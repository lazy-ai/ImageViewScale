# ImageViewScale
ImageView缩放不受限制
```
 private void scale(String path){
        Point size = new Point();

        //获取屏幕的尺寸
        WindowManager wm = (WindowManager) this.getSystemService(Context.WINDOW_SERVICE);
        wm.getDefaultDisplay().getSize(size);

        //屏幕宽度
        int screenWidth = size.x;
        int screenHeight = size.y;

        //获取图片的原始宽度
        BitmapFactory.Options options = new BitmapFactory.Options();
        options.inJustDecodeBounds = true;
        BitmapFactory.decodeFile(path, options);
        int imageWidth = options.outWidth;
        int imageHeight = options.outHeight;

        float scaleRate = screenWidth * 1.0f / imageWidth;
        float scaleRateh = screenHeight * 1.0f / imageHeight;

        //设置matrix
        Matrix matrix = new Matrix();

        //设置放缩比例
        matrix.setScale(scaleRate, scaleRateh);

        iv_chat_bg.setImageMatrix(matrix);
    }
```
