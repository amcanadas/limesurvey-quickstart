LimeSurvey on OpenShift
=========================
LimeSurvey allows users to quickly create intuitive, powerful, online question-and-answer surveys that can work for tens to thousands of participants without much effort. The survey software itself is self-guiding for the respondents who are participating. 

More information can be found at the official LimeSurvey website (www.limesurvey.org)

Running on OpenShift
--------------------

Create an account at https://www.openshift.com and install the client tools (rhc 'rhc setup' first)

Create a PHP application

	rhc app create limesurvey php-5.3 mysql-5.1 --from-code=https://github.com/amcanadas/limesurvey-quickstart.git

That's it, you can now checkout your application at:

	http://limesurvey-$yournamespace.rhcloud.com/limesurvey

Note: to get database configuration information use

	rhc ssh limesurvey
	env | grep MYSQL

to resolve tmp access problem:

	chmod a+w app-root/runtime/repo/php/limesurvey/tmp
	mkdir app-root/runtime/repo/php/limesurvey/tmp/assets