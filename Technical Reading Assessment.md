# Step 3: Technical Reading Assessment #
**1. What does the command "bundle gem foodie" do?**  
It creates a gem called foodie using bundler, which involves a scaffold directory for the gem. The files created by the command are:  
**Gemfile**: manages gem dependencies.  
**Rakefile**: adds the build, install and release tasks.  
**.gitignore**: ignores anything in the pkg directory, anything with a .gem extension, and the bundle directory,  
**foodie.gemspec**: where we provide information for Rubygems' consumption (the gem's name, description, and homepage, etc.) and specifies the dependencies that our gem needs to run.  
**lib/foodie.rb**: defines our gem's code, and is required by Bundler when our gem is loaded. It sets up our gem's environment.  
**lib/foodie**: contains all the code for the gem.  
**lib/foodie/version.rb**: defines a foodie module which includes a version constant that we update when we release a new version.  
  
**2. In what folder do we put our test files?**  
In the "spec" folder.  
  
**3. What do we need to write to add the activesupport (version 4.0.0) dependency to our gemspec?**  
spec.add\_dependency "activesupport", "~> 4.0.0"  
  
**4. What steps need to be taken to write a generator?**  
Define a generator class inheriting from Thor::Group. All the methods in this class will be run when "start" is called on it. Make sure to require 'thor/group' in the class file.  
Include Thor::Actions module in this class, this is needed for defining helper methods needed for the generator (example: method for creating a directory). 
Define arguments that will be passed on to the generator using 'argument'.  
Define class method self.source_root to set the source path for the generator.  
Require the generator class in the CLI class file.  
