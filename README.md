# lib_update_action
私有库repo自动更新版本


## Example usage
    name: 'update pob lib'
    on: 
      create:
        tags: 
          - v*
    
    jobs:
      pod_lib_update:
        runs-on: macos-latest
    
        steps: 
          - name: Checkout
            uses: actions/checkout@v2
    
          - name: pod lib update
            uses: realPX/pod-lib-update-action@1.0.0
            with:
              spec_repo_url: https://realPX:${{secrets.ACCESS_TOKEN}}@github.com/realPX/PanKitSpec.git  
              spec_file_path: /PanKitSpec.podspec
              
