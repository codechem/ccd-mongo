
[![Build Status](https://travis-ci.org/codechem/ccd-ng2.svg?branch=master)](https://travis-ci.org/codechem/ccd-ng2)

<div style="display:flex;align-items:center;>
<label style="height:30px;height: 40px; line-height: 30px; padding-right: 20px;">
    
</label>
<a href="https://github.com/codechem/ccd" style="padding-right: 20px;display:flex;align-items:center;"">
    <label style="height:30px;height: 40px; line-height: 30px;padding-right: 10px;">
        <b>NG2 Decorator for CCD Framework</b>
    </label>
    <img style="height:60px" src="https://raw.githubusercontent.com/codechem/ccd-snippets/master/images/ccdLogo.png"></img>
</a>
</div>

## CCD-MONGO

Mongoose based service and CCD controller
Also implements the basic CRUD methods

### Example CCContrllerService
```typescript
...
interface User extends mongoose.Document{
    Username:string
}

class UserCtrl extends CCServiceController<User>{
    @get('/:username')    
    byUsername(req, res){
        return this.model.findOne({Username:username});
    }
}
//the mongoose model needs to be defined
mongoose.Model<User>('User', new mongoose.Schema({
    Username:String
});

app.use('/', new UserCtrl('User').router);
app.listen(3000);
```

### Note

If you like to be more structured and have the db methods in a separate class then you can use the ```CCService<T>``` class for that.

