# Lab Report 5

    CPATH=".:lib/hamcrest-care-1.3.jar:lib/junit-4.13.2.jar"
    rm -rf student submission
    git clone $1 student-submission > cloning.txt
    cp TestListExamples.java student-submission/
    cp -r lib student-submission
    cd student-submission
    if [ ! -f "ListExamples.java" ]
    then
            echo "Unable to locate ListExamples.java, unable to grade."
            exit 1
    fi
    echo "compiling files"
    javac -cp $CPATH TestListExamples.java ListExamples.java
    if [ $? -ne 0 ]
    then
            echo "ListExamples.java did not compile"
            exit 1
    fi
    echo "running files"
    java -cp $CPATH org.junit.runner.JUnitCore TestListsExamples > results.txt 2> error.txt
    grep -q "Failure" results
    if [ $? -eq 0 ]
    then
            echo "All tests did not pass on this repository"
    fi
    grep -q "Filter" results.txt
    if [ $? -eq 0 ]
    then
            echo "All tests did not pass on this repository"
    else
            echo "Filter method passes tests."
    fi
    grep -q "Merge" results.txt
    if [ $? -eq 0 ]
    then
            echo "All tests did not pass on this repository"
    else
            echo "Merge method passes tests."
    fi
    echo "Done grading"

