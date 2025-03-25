# Zfuzz

| Function Name                 | Goal                                                                 | Related Functions                         |
|-------------------------------|----------------------------------------------------------------------|-------------------------------------------|
| **abs**                       | Calculate absolute value of integers                                | min, max                                  |
| **adjustRate** (FuzzStats)    | Dynamically adjust request rate based on error ratio                | reportMetrics, memoryGuard                |
| **analyzeDynamicContent**     | Detect dynamic markers like forms/timestamps in HTML                | detectDynamicContent, calculateStructureHash |
| **analyzeRequests** (FuzzStats)| Generate real-time console status messages                         | reportMetrics, getRecentRequestsPreview   |
| **buildURL**                  | Construct fuzzed URLs with path handling                            | preserveExtension, normalizePath          |
| **calculateResponseDeviation**| Compute response time standard deviation                            | recordRequest, reportMetrics              |
| **calculateStructureHash**    | Create DOM structure fingerprint                                    | normalizeHTML, domSimilarity              |
| **calculateTimeVariance**     | Compare response time to cluster average                            | recordRequestMetrics, adjustRate          |
| **calculateVariance**         | Measure response difference from baselines                          | domSimilarity, headerSimilarity           |
| **checkBlockReasons**         | Identify WAF/security blocking indicators                           | isWAFResponse, getSecurityHeaders         |
| **classifyError**             | Categorize network errors (timeout/reset/etc)                       | sendRequest, handleRequestError           |
| **createHTTPClient**          | Configure HTTP client with timeouts/transports                      | processTarget, worker                     |
| **createResponseSignature**   | Generate fingerprint for server response                            | calculateDOMStructure, detectDynamicContent |
| **debugSaveResponse**         | Write response HTML to disk for debugging                           | processFinalResponse, sendRequest         |
| **generateCalibrationPaths**  | Create paths for baseline error detection                           | runCalibration, shouldSkipResponse        |
| **getSecurityHeaders**        | Extract security headers from responses                             | checkBlockReasons, createResponseSignature|
| **handleRedirects**           | Follow and analyze redirect chains                                  | sendRequest, getRedirectPattern           |
| **memoryGuard**               | Prevent OOM crashes by monitoring allocations                       | adjustRate, processTarget                 |
| **normalizeRedirectPattern**  | Standardize redirect paths for pattern matching                     | findCommonBase, simplifyPattern           |
| **parseFlags**                | Parse command-line arguments                                        | main, createOutputDir                     |
| **processTarget**             | Coordinate fuzzing for a single host                                | worker, runCalibration, sendRequest       |
| **reportMetrics** (FuzzStats) | Display live progress/statistics in console                         | getProgressBar, getStatusColor            |
| **sendRequest**               | Execute HTTP request with retry logic                               | handleRedirects, recordRequestMetrics     |
| **shouldFilterDOMHash**       | Filter duplicate DOM structures                                     | processFinalResponse, globalDOMHashes     |
| **startDebugMonitor**         | Enable metrics logging to file                                      | CaptureSnapshot, log (FuzzStats)          |
| **validateResponse**          | Check if response should be processed                               | sendRequest, processFinalResponse         |
| **worker**                    | Goroutine for parallel request processing                           | processTarget, warmupTarget               |
