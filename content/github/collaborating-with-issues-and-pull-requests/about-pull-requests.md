  if (serve) {
    win.webContents.openDevTools();

    require('electron-reload')(__dirname, {
      electron: `${__dirname}/node_modules/electron`,
    });
    win.loadURL('http://localhost:4200');
  } else {
    win.loadURL(
      url.format({
        pathname: path.join(__dirname, 'dist/index.html'),
        protocol: 'file:',
        slashes: true,
      })
    );
  }
