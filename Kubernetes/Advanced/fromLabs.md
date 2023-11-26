# Sprawdzanie podów na konkretnym node'ie

Aby zobaczyć, które pod'y działają na konkretnym węźle w klastrze Kubernetes, możesz użyć polecenia `kubectl` w połączeniu z komendami `kubectl get pods` oraz `kubectl describe node`.

Oto kroki:

1. **Pobierz listę węzłów:**
   Uruchom poniższą komendę, aby uzyskać listę węzłów w twoim klastrze:

   ```bash
   kubectl get nodes
   ```

   Zidentyfikuj nazwę węzła, który cię interesuje.

2. **Pobierz pod'y na konkretnym węźle:**
   Uruchom poniższą komendę, aby uzyskać pod'y działające na konkretnym węźle:

   ```bash
   kubectl get pods --field-selector spec.nodeName=NAZWA_WĘZŁA
   ```

   Zamień `NAZWA_WĘZŁA` na nazwę konkretnego węzła, który cię interesuje.

3. **Alternatywnie, użyj `kubectl describe`:**
   Możesz również użyć `kubectl describe node`, aby uzyskać szczegółowe informacje o węźle, w tym listę pod'ów działających na nim. Uruchom poniższą komendę:

   ```bash
   kubectl describe node NAZWA_WĘZŁA
   ```

   Zamień `NAZWA_WĘZŁA` na nazwę konkretnego węzła.

To dostarczy szczegółowych informacji o wybranym węźle, w tym pod'ach działających na nim.

Pamiętaj, że zdolność do uzyskania informacji o węzłach i pod'ach może zależeć od ustawień RBAC (Role-Based Access Control) w Kubernetes. Upewnij się, że masz odpowiednie uprawnienia do dostępu do tych informacji.

-----

# Brak mozliwości drainowania node'a z racji na deamon set

Jeśli spotykasz się z terminem "daemonset-managed pods" w kontekście Kubernetes, oznacza to, że używany jest obiekt `DaemonSet` do zarządzania konkretnymi podami (kontenerami) na węzłach klastra. 

W Kubernetes, `DaemonSet` to obiekt, który zapewnia, że co najmniej jedna instancja poda działa na każdym węźle w klastrze. W praktyce oznacza to, że, jeśli dodajesz nowy węzeł do klastra, `DaemonSet` automatycznie tworzy nową instancję poda na tym węźle. Podobnie, gdy węzeł jest usuwany, instancja poda również jest usuwana.

`DaemonSet` jest często używany do uruchamiania infrastruktury systemowej, monitorowania, loggingu czy innych komponentów, które muszą być dostępne na każdym węźle klastra. Dzięki temu można zapewnić, że te usługi są równomiernie rozproszone po całym klastrze.

Przykładowy obiekt `DaemonSet` może wyglądać tak:

```yaml
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: example-daemonset
spec:
  selector:
    matchLabels:
      app: example
  template:
    metadata:
      labels:
        app: example
    spec:
      containers:
      - name: example-container
        image: example-image:latest
```

W powyższym przykładzie:

- `selector` definiuje, które poda będą zarządzane przez `DaemonSet`.
- `template` definiuje szablon dla poda, który będzie uruchamiany na każdym węźle.

W efekcie, każdy węzeł w klastrze będzie uruchamiał jeden pod zgodny z tym szablonem.

**W celu drainowania node'a z jedną instancją poda w trybie domyślnym zarządzanego przez DeamonSet** musimy napisać takie polecenie.

```bash
kubectl drain NAZWA_WEZŁA --ignore-deamonsets

```
-----

# Informacje o upgrade'ach

```bash
kubeadm upgrade plan

```

# Cała instrukcja jak upgrade'ować klaster

[upgrading kubeadm clusters](https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-upgrade/)


# Pobranie wszystkich informacji i zapisanie ich w pliku konfiguracyjnym 

```bash
kubectl get all --all-namespaces -o yaml > plikkonfiguracyjny.yaml

```

# Sprawdzenie czy włączona jest mozliwość przekazywania pomiędzy interfejsami 

```bash
cat /proc/sys/net/ipv4/ip_forward

```
W katalogu `/proc/sys/net/ipv4/` znajdują się pliki stosu ipv4.
Liczba 1 w tym pliku wskazuje na pozwolenie. Potrzebne jest to kiedy maszyna działa jako host a potrzebne jest przekazywanie pomiędzy interfejsami. 

Ustawienie liczby 1 w pliku ip_forward jest niestałe. 
Aby stan się utrzymywał wymagane jest:

```bash

echo "net.ipv4.ip_forward = 1" >> /etc/sysctl.conf
sysctl -p
```

Bez włączenia pozwolnia na nic zdadzą się próby dodawania wybranej sieci przez gatewaye. Przykład:

```bash
ip route add default via 192.168.1.1

```
# Konfiguracja serwera DNS

```bash

cat /etc/resolv.conf

```
Host najpierw zagląda do /etc/host i tam szuka wpisu dns, dopiero później zajmuje się adresem serwera dns. Lokalny plik `/etc/hosts` ma pierwszeństwo.

# Opcja search w pliku /etc/resolv.conf

W pliku `/etc/resolv.conf` na systemach Unix/Linux, opcja `search` służy do zdefiniowania domeny, która będzie automatycznie dopisywana do niepełnych nazw domenowych, które nie zawierają kropki (.) na końcu.

Przykładowy wpis z opcją `search` może wyglądać tak:

```
search example.com
```

W tym przypadku, jeśli użytkownik wpisuje niepełną nazwę domenową, np. "server", system automatycznie dołącza do niej domenę `example.com`. W efekcie, system będzie próbował rozwiązać to jako "server.example.com".

Przykład użycia:

- Użytkownik wpisuje: `ping server`
- System automatycznie przekształca to na: `ping server.example.com`

Dzięki temu mechanizmowi użytkownik nie musi wpisywać pełnych nazw domenowych w przypadku lokalnych zasobów sieciowych. Opcja `search` jest szczególnie przydatna w sieciach lokalnych, gdzie istnieje wspólna domena dla wielu zasobów.

Można również podać więcej niż jedną domenę, oddzielając je spacjami:

```
search example.com subdomain.example.com
```

Wówczas system będzie próbował automatycznie dopisywać obie domeny do niepełnych nazw domenowych.

# Róznica pomiędzy ping - nslookup - dig

nslookup i dig nie zaglądają do pliku `/etc/hosts` a patrzą bezpośrednio do pliku `/etc/resolv.conf`.