# cli
A community command-line tool for validating UCP manifests directly from your terminal or CI/CD pipeline. 

Features                                                                                                  
                                                                                                            
- Live Verification: Force a real-time check against the UCP Validator API                                
- CI/CD Ready: Proper exit codes (0 for verified, 1 for failure) to gate deployments                      
- Scriptable: --json output for easy parsing with jq                                                      
                                                                                                            
Installation                                                                                              
                                                                                                            
Linux / CI (GitHub Actions)                                                                               
wget https://github.com/ucpchecker/cli/releases/download/v1.0.0/ucp-linux-amd64                           
chmod +x ucp-linux-amd64                                                                                  
./ucp-linux-amd64 check yourdomain.com                                                                    
                                                                                                            
Mac (Apple Silicon)                                                                                       
wget https://github.com/ucpchecker/cli/releases/download/v1.0.0/ucp-mac-arm64                             
chmod +x ucp-mac-arm64                                                                                    
./ucp-mac-arm64 check yourdomain.com                                                                      
                                                                                                            
Windows                                                                                                   
                                                                                                            
Download ucp-windows.exe from https://github.com/ucpchecker/cli/releases and run via PowerShell.          
                                                                                                            
Usage                                                                                                     
                                                                                                            
# Live check (forces fresh verification)                                                                  
ucp check mystore.com                                                                                     
                                                                                                            
# Cached status lookup (fast, no external requests)                                                       
ucp status mystore.com                                                                                    
                                                                                                            
# JSON output for scripting                                                                               
ucp check mystore.com --json                                                                              
                                                                                                            
# Use in CI/CD                                                                                            
ucp check mystore.com || exit 1  
