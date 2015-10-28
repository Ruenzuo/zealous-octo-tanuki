desc "Bootstraps this project"
task :bootstrap do
  system "bundle exec pod install" 
end

desc "Packs ipa"
task :pack do
  system "xcodebuild -workspace TestingApp.xcworkspace -scheme TestingApp -archivePath build/TestingApp.xcarchive archive"
  system "xcrun xcodebuild -exportArchive -exportOptionsPlist export-options.plist -archivePath build/TestingApp.xcarchive -exportPath build/"
end

desc "Uploads ipa to iTunes Connect"
task :upload do
  system "bundle exec ipa distribute:itunesconnect -f build/TestingApp.ipa -u -a ruenzuo.io@gmail.com -p $PASSWORD --verbose -i 851222693"
end
