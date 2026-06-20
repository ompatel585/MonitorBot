                         +-------------+
                         |  Next.js UI |
                         +------+------+
                                |
                                |
                                v

                     +--------------------+
                     |     NestJS API     |
                     +----+----------+----+
                          |          |
                          |          |
                          v          v

                    PostgreSQL      Redis
                       |              |
                       |              |
                       +------+-------+
                              |
                              v

                         BullMQ Queue
                              |
                              v

                      Monitoring Worker
                              |
                              v

                    External APIs/Websites


User creates monitor
        ↓
Nest API stores monitor
        ↓
BullMQ creates repeatable job
        ↓
Worker executes job
        ↓
Website checked
        ↓
Result stored
        ↓
Incident created if needed
        ↓
WebSocket event emitted
        ↓
Frontend updates