# meta Ordner  

Gibt an welche anderen Rollen (als Abhängigkeit) vor dem ausführen der eigentlichen Rolle ausgeführt werden müssen.

## Beispiele

Um die Docker Engine installieren zu können, muss zuerst das MMS_AMCS_COMMONS Repo auf dem Zielserver eingebunden werden. Die Einbindung findet in einer anderen Rolle statt. Um sicherzugehen, dass erst die Rolle ausgeführt wird, welche das Repo einbindet, wird diese Rolle als dependencie (Abhängigkeit) zur Docker Engine Rolle in den meta Ordner eingetragen

## Verwendung

Die Abhängigkeiten werden wie im folgenden Beispiel in der main.yml im meta Ordner definiert.

Beispiel:

```yaml
---
dependencies:
 - role: volumes
```

Dieses Beispiel legt fest, dass er die Rollen: volumes und auditd ausgeführt werden müssen, bevor man mit dem eigentlichen Task beginnt. 