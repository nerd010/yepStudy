source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '9.0'
use_frameworks!

def pods
    pod 'AutoReview'
    pod 'AudioBot'
    pod 'Appsee'
    pod 'DeviceGuru'
    pod 'FXBlurView'
    pod 'TPKeyboardAvoiding'
    pod 'pop'
    pod 'Base64'
    pod 'SocketRocket'
    pod 'JPush'
    pod 'Fabric'
	pod 'Texture'
	pod 'FayeSwift'
	pod 'Alamofire', '~> 4.5'
end

target 'yepstudy' do
    pods

    target 'yepstudyTests' do
        inherit! :search_paths
    end
end

post_install do |installer|
    puts 'Allow app extension api only:'
    installer.pods_project.targets.each do |target|
        case target.name
        when 'Base64', 'SocketRocket'
            target.build_configurations.each do |config|
                config.build_settings['APPLICATION_EXTENSION_API_ONLY'] = 'YES'
                puts 'X...' + target.name
            end
        else
            puts '....' + target.name
        end
    end
end

