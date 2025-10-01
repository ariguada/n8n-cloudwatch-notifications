## Test 1: Standard Alarm Notification
**Description:** Tests a CloudWatch alarm in ALARM state, sent to Telegram chat.

```bash
curl -X POST https://your-user.app.n8n.cloud/webhook-test/sns-alert \
  -H "Content-Type: application/json" \
  -d '{"Type":"Notification","MessageId":"a1b2c3d4-5678-9012-3456-789012345678","TopicArn":"arn:aws:sns:us-east-1:123456789012:CloudWatchAlerts","Subject":"ALARM: TestAlarm","Message":"{\"AlarmName\":\"TestAlarm\",\"NewStateValue\":\"ALARM\",\"NewStateReason\":\"Threshold breached for testing.\"}","Timestamp":"2025-10-01T13:28:00.123Z"}'
```
![test01.png](images/test01.png)

## Test 2: High CPU Utilization Alarm
**Description:** Tests a CloudWatch alarm for high CPU usage in ALARM state, sent to Telegram chat.

```bash
curl -X POST https://your-user.app.n8n.cloud/webhook-test/sns-alert \
  -H "Content-Type: application/json" \
  -d '{"Type":"Notification","MessageId":"b2c3d4e5-6789-0123-4567-890123456789","TopicArn":"arn:aws:sns:us-east-1:123456789012:CloudWatchAlerts","Subject":"ALARM: CPUUtilizationHigh","Message":"{\"AlarmName\":\"CPUUtilizationHigh\",\"NewStateValue\":\"ALARM\",\"NewStateReason\":\"CPU usage exceeded 80% for 5 minutes.\"}","Timestamp":"2025-10-01T13:32:00.456Z"}'
```
![test02.png](images/test02.png)

## Test 3: OK State Notification
**Description:** Tests a CloudWatch alarm returning to OK state, sent to Telegram chat.

```bash
curl -X POST https://your-user.app.n8n.cloud/webhook-test/sns-alert \
  -H "Content-Type: application/json" \
  -d '{"Type":"Notification","MessageId":"c3d4e5f6-7890-1234-5678-901234567890","TopicArn":"arn:aws:sns:us-east-1:123456789012:CloudWatchAlerts","Subject":"OK: DatabaseLatency","Message":"{\"AlarmName\":\"DatabaseLatency\",\"NewStateValue\":\"OK\",\"NewStateReason\":\"Database latency returned to normal (below 100ms).\"}","Timestamp":"2025-10-01T13:32:00.789Z"}'
```
![test03.png](images/test03.png)
