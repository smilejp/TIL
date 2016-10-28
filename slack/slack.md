# fun slack


### 퇴근봇 만들기
* 이상한 모임 2016 세미나 @shia 님 발표자료 이용(https://github.com/weirdmeetup/emocon/tree/gh-pages/2016fw/slides)

```
const exec = require('child_process').exec;
const msg = "야근도 그만하고 집에 가세요~ 술마시지 말고 집으로.... :octocat:"
const payload = `payload={"channel": "#general", "username":"봇", "text":"${msg}"}`
const url = "https://hooks.slack.com....."

exports.handler = (event, context, callback) => {
    // TODO implement
    const cmd = `curl -X POST --data-urlencode '${payload}' ${url}`;
    child = exec(cmd, (error) => {
        // resolve with result of process
        context.done(error, "incoming hook is triggered");
    });


    // log process stdout and stderr
    child.stdout.on('data', console.log);
    child.stderr.on('data', console.error);


    # nodejs 4.3에서는 callback()을 이용해서 성공 / 실패를 남긴다.
    # 성공 - callback(null, "message");
    # 실패 - callback("fail", "message");
    # http://docs.aws.amazon.com/lambda/latest/dg/nodejs-prog-model-handler.html#nodejs-prog-model-handler-callback
    callback(null, 'Hello from Lambda');
};
```

* aws lambda에서 function을 만들고 test 버튼을 누르면 json 값을 입력할 수 있는 창이 뜨는데 여기에 값을 설정하면 event로 전달된다.

### CloudWatch에서 cron 설정
* CloudWatch에서 cron으로 시간 설정은 UTC로 설정해야 하므로 9시간을 빼주면된다.
* cron 설정법 - http://docs.aws.amazon.com/lambda/latest/dg/tutorial-scheduled-events-schedule-expressions.html
* cron(Minutes Hours Day-of-month Month Day-of-week Year)
```
 cron(00 12 ? * MON-FRI *)
```

### apex 설치
* 공식 홈(http://apex.run)
* 윈도우는 binary를 다운받아서 설치해야 한다(https://github.com/apex/apex/releases)
