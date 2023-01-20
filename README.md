# telegraf-output-plugin-amqp_ext

## Build an executable **amqp_ext**
Run the following lines in command window
``
go mod init cmd/main.go
``
``
go mod tidy
``
``
go build -o amqp_ext cmd/main.go
``
## Apply the executable **amqp_ext** in a telegraf program
Write in a config file containing the config for amqp_ext output plugin
#### **`path/to/config.conf`**
``
[[inputs.CERTAIN_INPUT_PLUGIN]]
  ...
  
[[outputs.execd]]
  name_suffix = "_amqp_ext"
  command = ["path/to/telegraf-output-plugin-amqp_ext/amqp_ext", "-config", "path/to/telegraf-output-plugin-amqp_ext/cmd/plugin.conf"]
``
An input plugin is necessary for running the output plugin amqp_ext.
Run the telegraf with config.conf
``
telegraf --config path/to/config.conf
``
