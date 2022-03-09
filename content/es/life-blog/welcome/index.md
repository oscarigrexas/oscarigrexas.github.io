---
title: "Welcome"
date: 2022-03-04T17:04:11+01:00
draft: true
---

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum condimentum, turpis sit amet fermentum luctus, leo magna varius ligula, a dictum justo massa vel nisi. Suspendisse lacus tortor, viverra nec mollis vitae, luctus non neque. Proin blandit rutrum ipsum sed lobortis. Duis luctus arcu quis ipsum pharetra consectetur. Maecenas id urna id ipsum tincidunt iaculis et ac enim. Phasellus condimentum dolor tempor, aliquam metus pretium, fermentum urna. Integer condimentum purus magna.

```python
class SensorDataRepository:
    """
    Name Repository class
    Implements the interface to the database. In this case it is a list of strings
    """

    @staticmethod
    def get_last_batch(batch_size: int) -> Union[Dict[str, List[DataPoint]], None]:
        """Returns the lastest batch of sensor data in the database"""
        logger.info(f"Retrieving the latest batch of sensor data: {batch_size} points")
        try:
            sensor_data = {}
            for sensor_id, records in sensor_data_database.items():
                data_points = [DataPoint(**record) for record in records[:batch_size]]
                logger.debug(f"Sensor {sensor_id}, {len(data_points)} points selected")
                sensor_data[sensor_id] = data_points
            return sensor_data
        except IndexError:
            return None
```

Nunc porttitor, ex non auctor viverra, nunc odio porta ligula, sed ullamcorper velit ante ac arcu. Mauris eu ligula molestie metus mattis accumsan in in lectus. Cras eu ligula massa. Sed tempus est eget justo imperdiet, eu venenatis sapien auctor. Vestibulum ut dui a arcu pretium euismod. Nulla scelerisque nulla non eros eleifend, fermentum mollis diam tempor. Phasellus risus nisi, pellentesque in quam maximus, elementum semper lectus. Vivamus luctus, quam ut euismod placerat, nisi dolor fermentum lacus, eget egestas felis tortor in est. Curabitur sit amet urna velit. Sed quis nisl pulvinar, convallis eros sit amet, euismod mauris. Aenean ante leo, vulputate ac augue eu, porttitor tempus mi. Aenean faucibus vestibulum metus id semper. In porttitor eu tellus quis consequat. Maecenas egestas lacus id ante commodo efficitur.