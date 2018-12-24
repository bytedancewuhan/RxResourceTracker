# Uncomment this line to define a global platform for your project
platform :ios, '9.0'

target 'RxSwiftResourceTracker' do
  # Uncomment this line if you're using Swift or would like to use dynamic frameworks
  use_frameworks!

  pod 'RxSwift'
  
  post_install do |installer|
      installer.pods_project.targets.each do |target|
          if target.name == 'RxSwift'
              target.build_configurations.each do |config|
                  if config.name == 'Debug'
                      config.build_settings['OTHER_SWIFT_FLAGS'] ||= ['-D', 'TRACE_RESOURCES']
                  end
              end
          end
      end
  end 
end
