# 数据协议

```java
public enum d {
    IR_SEND(0),
    IR_SEND_MISS(1),
    IR_SEND_ACK(2),
    IR_SEND_ID(3),
    IR_SEND_ID_ACK(4),
    IR_LEARN_START(5),
    IR_LEARN_STOP(6),
    IR_LEARN_ACK(7),
    IR_LEARN_TIMEOUT(8),
    IR_LEARN_CODE(9),
    IR_LEARN_CODE_MISS(10),
    IR_LEARN_CODE_ACK(11),
    IR_TIMER_READ(12),
    IR_TIMER_MODIFY(13),
    IR_TIMER_ADD(14),
    IR_TIMER_DELETE(15),
    IR_BATTERY_DATA(16),
    IR_TH_DATA(17),
    IR_GET_KEY(24),
    IR_GET_KEY_ACK(25),
    IR_SET_NAME(26),
    IR_SET_NAME_ACK(27),
    IR_SEND_PACKET_ACK(28),
    IR_SCENE_READ(30),
    IR_SCENE_READ_ACK(31),
    IR_SCENE_SET(32),
    IR_SCENE_SET_ACK(33),
    IR_PACKET_NONE(255);
    
    public final int C;

    private d(int i) {
        this.C = i;
    }

    public static d a(byte b) {
        int a = a.a(b);
        for (d dVar : values()) {
            if (dVar.C == a) {
                return dVar;
            }
        }
        return IR_PACKET_NONE;
    }
}
```