---
title: 手順 2:Web プロジェクトの配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb775a89-2e2d-43e5-94ae-f75c1756dbd7
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f39a8b60918f2dd97ea9442fca5dda961e2cafde
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363265"
---
# <a name="step-2-deploy-the-web-project"></a>手順 2:Web プロジェクトをデプロイします。
![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")  
  
 **所要時間:** 5 分  
  
 この手順で生成された Web プロジェクトを発行する[手順 1。Web プロジェクトを作成するアダプター サービス開発ウィザードを使用して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)インターネット インフォメーション サービス (IIS) にします。  
  
## <a name="prerequisites"></a>前提条件  
 作成したこの手順を完了する[手順 1。Web プロジェクトを作成するアダプター サービス開発ウィザードを使用して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)します。 Web サーバーは、HTTPS 通信を有効にインストールされている SSL 証明書も必要です。  
  
## <a name="compile-and-deploy-the-web-project"></a>コンパイルして、Web プロジェクトの配置  
  
1. Visual Studio では、以前に作成 EchoWeb プロジェクトを読み込みます。  
  
2. Visual Studio コマンド プロンプトを開きます。  
  
3. C:\tutorials\echoweb フォルダーから、コマンド プロンプトで次のコマンドを入力し、ENTER キーを押します。  
  
    **sn /k EchoWebKey.snk**  
  
    確認のメッセージでは、**キーのペア EchoWebKey.snk に書き込まれる**コマンドラインで表示されます。  
  
4. コマンド プロンプトを閉じます。  
  
5. **ソリューション エクスプ ローラー**EchoWeb プロジェクトを右クリックして選択し、 **Web サイトの発行**します。  
  
6. **Web サイトの発行** ダイアログ ボックスの**ターゲットの場所**、入力 **http://machinename/EchoWeb**します。 選択**このプリコンパイル済みサイトを更新可能**、**固定名およびシングル ページ アセンブリを使用する**、および**プリコンパイル済みアセンブリで厳密な名前を有効にする**します。 **ファイルの場所をキー**フィールドで省略記号をクリックします **([...])。** ボタンをクリックし、以前は、作成 EchoWebKey.snk ファイルを選択し、順にクリックします**OK**します。  
  
7. Web サイトが正しく作成されたことを確認するには、Internet Explorer を起動、入力 **"<http://localhost/EchoWeb/EchoOutboundContract.svc>"** でアドレス バー、および ENTER キーを押します。 EchoOutboundContractClient を説明する Web ページが表示されます。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 IIS に Web プロジェクトを発行するだけです。  
  
## <a name="next-steps"></a>次の手順  
 これでコンパイルされ、プロジェクトのデプロイに進んで[手順 3。アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: IIS でエコー アダプターをホストする](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)