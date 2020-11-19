## Hetero Neural Network Configuration Usage Guide.

#### Example Tasks

This section introduces the dsl and conf for different types of tasks.

1. Binary Train Task:

    example-data: (1) guest: breast_hetero_guest.csv (2) host: breast_hetero_host.csv  
    
    dsl: test_hetero_nn_dsl.json

    runtime_config : test_hetero_nn_binary_conf.json

2. Multi-label Train Task:
    
    example-data: (1) guest: vehicle_scale_hetero_guest.csv  
                  (2) host: vehicle_scale_hetero_host.csv  
    
    dsl: test_hetero_nn_dsl.json

    runtime_config: test_hetero_nn_multi_conf.json

3. Train Task With Early Stopping Strategy:

    example-data: (1) guest: breast_hetero_guest.csv  (2) host: breast_hetero_host.csv  
    
    dsl: test_hetero_nn_binary_with_early_stop_dsl.json

    runtime_config : test_hetero_nn_binary_with_early_stop_conf.json

    This feature support since FATE-1.4, please have a look at the param "early_stopping_rounds", "metric", "validation_freqs"

Users can use following commands to run a task.

    flow job submit -c ${runtime_config} -d ${dsl}

Moreover, after successfully running the training task, you can use it to predict too.