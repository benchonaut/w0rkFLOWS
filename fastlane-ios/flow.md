



###MAKE SCHEME SHARED

->solution needed


##CREATE FASTFILE (or load)

#->set username in lanes
#->

export FASTLANE_PASSWORD=$(read -n flpwd;echo $flpwd)

##UNLOCK KEYCHAIN FOR BUILD SIGNING

security unlock-keychain -p MY_PASS ~/Library/Keychains/login.keychain
security set-key-partition-list -S apple-tool:,apple:,codesign: -s -k MY_PASS ~/Library/Keychains/login.keychain
security set-keychain-settings ~/Library/Keychains/login.keychain


fastlane beta #(first gym , then testflight)
