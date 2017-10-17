---
title: "手順 2: Web プロジェクトを展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb775a89-2e2d-43e5-94ae-f75c1756dbd7
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85cef88de4e8fa05bb50840002a0f344b1f0b350
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
---
# <a name="step-2-deploy-the-web-project"></a>手順 2: Web プロジェクトを展開します。
![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **所要時間:** 5 分  
  
 この手順で生成された Web プロジェクトをパブリッシュします[手順 1: Web プロジェクトを作成するアダプター サービス開発ウィザードを使用して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)インターネット インフォメーション サービス (IIS) にします。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を完了する必要がありますを行った[手順 1: Web プロジェクトを作成するアダプター サービス開発ウィザードを使用して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)です。 Web サーバーは、HTTPS 通信を有効にインストールされている SSL 証明書も必要です。  
  
## <a name="compile-and-deploy-the-web-project"></a>コンパイルして、Web プロジェクトの配置  
  
1.  Visual Studio では、以前に作成された EchoWeb プロジェクトを読み込みます。  
  
2.  Visual Studio コマンド プロンプトを開きます。  
  
3.  C:\tutorials\echoweb フォルダーから、コマンド プロンプトで次のコマンドを入力し、ENTER キーを押します。  
  
     **sn/k EchoWebKey.snk**  
  
     確認メッセージを**キー ペア EchoWebKey.snk に書き込まれる**、コマンド ラインで表示されます。  
  
4.  コマンド プロンプトを閉じます。  
  
5.  **ソリューション エクスプ ローラー**EchoWeb プロジェクトを右クリックし、、 **Web サイトの発行**です。  
  
6.  **Web サイトの発行** ダイアログ ボックスの**ターゲットの場所**、入力**http://machinename/EchoWeb**です。 選択**このプリコンパイル済みサイトを更新できるように**、**固定名およびシングル ページ アセンブリを使用する**、および**プリコンパイル済みアセンブリに厳密な名前を有効にする**です。 **ファイルの場所をキー**フィールドで省略記号ボタンをクリックして**([...])**ボタンをクリックし、以前作成した EchoWebKey.snk ファイルを選択し、をクリックして**OK**です。  
  
7.  Web サイトが正しく作成されたことを確認するには、Internet Explorer を起動、入力**"http://localhost/EchoWeb/EchoOutboundContract.svc"**でアドレス バー、および、ENTER キーを押します。 EchoOutboundContractClient を説明する Web ページが表示されます。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 IIS に Web プロジェクトをパブリッシュしただけです。  
  
## <a name="next-steps"></a>次の手順  
 進むことができますをコンパイルし、プロジェクトを展開した、[手順 3: アプリケーション定義ファイルの作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: IIS でエコー アダプターをホストします。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)