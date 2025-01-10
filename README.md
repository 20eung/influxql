# Grafana InfluxQL 예제

## Tag 사용하기

> Query

```
SELECT non_negative_derivative("ifHCInOctets", 1s) * 8 
FROM "snmp" 
WHERE $timeFilter 
  AND ("hostname"::tag =~ /MPLS_.$/ AND "ifName"::tag = '1/1/1')
GROUP BY "hostname", "ifName"
```

> Alias

```
$tag_hostname : $tag_ifName
```
