[![Build Status](https://travis-ci.org/abdullahselek/ASMapLauncher.svg?branch=master)]

# ASMapLauncher
ASMapLauncher is a library for iOS written in Swift that helps navigation with various mapping applications.

# Requirements
iOS 8.0+

# CocoaPods

CocoaPods is a dependency manager for Cocoa projects. You can install it with the following command:
	
	$ gem install cocoapods

To integrate ASMapLauncher into your Xcode project using CocoaPods, specify it in your Podfile:

	source 'https://github.com/CocoaPods/Specs.git'
	platform :ios, '8.0'
	use_frameworks!

	target '<Your Target Name>' do
    	pod 'ASMapLauncher', '1.0.1'
	end

Then, run the following command:

	$ pod install

# Usage

First initiate ASMapLauncher and check for a selected mapping application that installed on device

	mapLauncher = ASMapLauncher()
	var isInstalled = mapLauncher.isMapAppInstalled(ASMapApp.ASMapAppHEREMaps)
	
Then, launch selected mapping application

	if isInstalled {
		var destination: CLLocation! = CLLocation(latitude: 41.0053215, longitude: 29.0121795)
    	var fromMapPoint: ASMapPoint! = ASMapPoint(location: CLLocation(latitude: currenctCoordinate.latitude, longitude: currenctCoordinate.longitude), name: "", address: "")
        var toMapPoint: ASMapPoint! = ASMapPoint(location: CLLocation(latitude: destination.coordinate.latitude, longitude: destination.coordinate.longitude), name: "", address: "")
        mapLauncher.launchMapApp(ASMapApp.ASMapAppGoogleMaps, fromDirections: fromMapPoint, toDirection: toMapPoint)
    }

Supported mapping applications

	- Apple Maps
	- HERE Maps
	- Google Maps
	- Yandex Navigator
	- Citymapper
	- Navigon
	- The Transit App
	- Waze
	
# MIT License

	Copyright (c) 2015 Abdullah Selek

	Permission is hereby granted, free of charge, to any person obtaining a copy
	of this software and associated documentation files (the "Software"), to deal
	in the Software without restriction, including without limitation the rights
	to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
	copies of the Software, and to permit persons to whom the Software is
	furnished to do so, subject to the following conditions:

	The above copyright notice and this permission notice shall be included in all
	copies or substantial portions of the Software.

	THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
	IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
	FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
	AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
	LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
	OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
	SOFTWARE.
