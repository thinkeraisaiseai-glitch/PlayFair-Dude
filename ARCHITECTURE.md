# Architecture Overview

PlayFair Dude consists of:

1. Observer
   - Listens to server-side events only

2. Aggregator
   - Counts events in time windows

3. Evaluator
   - Applies transparent thresholds

4. Anonymizer
   - Enforces privacy rules

5. Exporter
   - Outputs summaries for dashboards or logs
