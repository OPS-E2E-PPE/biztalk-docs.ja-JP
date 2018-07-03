---
title: '手順 1: アダプター サービス開発ウィザードを使用して Web プロジェクトを作成する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ea0e33c-0d8d-4656-a6f0-3008b90f93f8
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fb8737f51f9e0b6afe3d61218f69015c1cd5d72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984035"
---
# <a name="step-1-use-the-adapter-service-development-wizard-to-create-the-web-project"></a>手順 1: アダプター サービス開発ウィザードを使用して Web プロジェクトを作成するには
![手順 4 の 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 10 分  
  
 この手順では、Visual Studio を使用してプロジェクトを作成し、[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]します。 [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]アダプター、操作、およびエンドポイントの構成に関する情報を収集し、それからを IIS に配置する Web プロジェクトを生成します。  
  
## <a name="prerequisites"></a>前提条件  
 ビルドし、デプロイで説明されている Echo サンプル[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)このチュートリアルを開始する前にします。  
  
### <a name="to-start-the-adapter-service-development-wizard"></a>アダプター サービス開発ウィザードを開始するには  
  
1.  Visual Studio を起動し、**ファイル**メニューで、**新規**、 をクリックし、 **Web サイト**します。  
  
2.  **新しい Web サイト** ダイアログ ボックスで、次の操作を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**言語**|クリックして**Visual c#** します。|  
    |**[テンプレート]**|クリックして**WCF アダプタ サービス**します。|  
    |**場所**|選択**ファイル システム**、し、入力**C:\Tutorials\EchoWeb**パスとして。|  
  
3.  **[OK]** をクリックします。  
  
4.  **へようこそ ページ**、 をクリックして**次**します。  
  
### <a name="to-select-the-adapter-and-uri"></a>アダプターと URI を選択するには  
  
1.  **サービス コントラクトを生成する操作を選択**] ページで、[ **echoAdapterBindingV2**から、**バインディングを選択**ドロップダウン ボックスの一覧し、順にクリックします**構成**します。  
  
2.  **セキュリティ**のタブ、**アダプターの構成**ダイアログ ボックスで、セット**クライアント資格情報の種類**に**ユーザー名**、を設定**ユーザー名資格情報**次のようにします。  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**ユーザー名**|username|  
    |**Password**|password|  
  
    > [!NOTE]
    >  ユーザー名とパスワードをここに入力は、ウィザードの手順を実行中に、アダプターへの接続にのみ使用し、ウィザードの完了後は保持されません。  
  
3.  をクリックして、 **URI プロパティ**タブをクリックし、次のようにプロパティを設定します。  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**アプリケーション**|LobApplication|  
    |**EnableAuthentication**|True|  
    |**ホスト名**|lobhostname|  
    |**EchoInUpperCase**|False|  
  
    > [!NOTE]
    >  ここで選択した URI のプロパティは、作成に使用する、 \<**クライアント**\>\<**エンドポイント**\> web.config ファイル内の要素。  
  
4.  をクリックして、**バインドのプロパティ**タブ。クリックして、既定値に注意してください**OK**します。  
  
    > [!NOTE]
    >  バインディングの値は生成に使用する、 \<**バインド**\>\<**echoAdapterBindingV2** \> web.config ファイル内の要素。  
  
### <a name="to-select-the-contract-and-operations"></a>コントラクトと操作を選択するには  
  
1.  **サービス コントラクトを生成する操作を選択**] ページで [ **Connect**します。  
  
2.  **カテゴリを選択**ツリーで、選択**メイン カテゴリ**します。 これによって、**利用可能なカテゴリと操作**一覧。  
  
    > [!NOTE]
    >  検索語句を入力することも、**カテゴリで検索**検索語句が含まれているすべての操作を検索するフィールド。  
  
3.  **利用可能なカテゴリと操作**一覧で、 **EchoGreetings**クリック**追加**。 EchoGreetings 操作を移動、**カテゴリと操作を追加**一覧。 ここで選択した操作は、ウィザードによって生成されたクライアント プロキシ コードを通じてクライアント アプリケーションに公開されます。  
  
     ![コントラクトと操作の選択](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")  
  
4.  **[次へ]** をクリックします。  
  
### <a name="to-configure-service-and-endpoint-behavior"></a>サービスとエンドポイントの動作を構成するには  
  
1.  **サービスとエンドポイント動作を構成する** ページで、次の値を入力します**サービス動作構成**:  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**EnableMetadataExchange**|True|  
    |**IncludeExceptionDetailsinFault**|True|  
    |**名前**|customServiceBehavior|  
    |**UseServiceCertificate**|False|  
  
     これらの値が設定に使用されます、 \< **serviceBehaviors**\>します。  
  
2.  次の値を入力します**エンドポイント動作の構成**:  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**名前**|customEndpointBehavior|  
    |**AuthenticationType**|**HTTPUsernamePassword**|  
    |**UsernameHeader**|MyUserHeader|  
    |**PasswordHeader**|MyPassHeader|  
  
     これらの値が指定するため、 **adapterSecurityBridgeType**で、<**endpointBehaviors** web.confg 内の要素。  
  
     ![エンドポイント構成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")  
  
3.  **[次へ]** をクリックします。  
  
### <a name="to-configure-the-binding"></a>バインドを設定する  
  
1. **サービス エンドポイントのバインドとアドレスの構成**] ページで、[、 **BindingConfiguration**エントリ**アドレスとコントラクトのバインディング構成**と省略記号をクリックします (**.**) ボタンをクリックします。  
  
2. **のバインドのカスタマイズ**ダイアログ ボックスで、セット**モード**に**TransportWithMessageCredential**、順にクリックします**OK**します。  
  
3. クリックして**適用**、順にクリックします**次**します。  
  
4. **概要**ページで、コントラクトと操作をこのプロジェクトで選択を確認し、クリックして**完了**します。 によって作成されたプロジェクト ファイルを含む EchoWeb ソリューションが表示されます、 [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順では使用して、 [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] Web の生成をホストでエコー アダプターの開発には、IIS に発行されると、プロジェクト[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)IIS で処理します。 結果として得られる Web プロジェクトでは、選択した操作にアクセスする Web サービスと WCF のクライアントを許可します。  
  
## <a name="next-steps"></a>次の手順  
 をビルドし、Web プロジェクトのデプロイに進む[手順 2: Web プロジェクトのデプロイ](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: エコー アダプターを開発する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)