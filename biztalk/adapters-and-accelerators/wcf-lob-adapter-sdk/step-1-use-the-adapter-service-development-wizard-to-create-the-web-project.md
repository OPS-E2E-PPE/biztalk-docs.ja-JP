---
title: "手順 1: Web プロジェクトを作成するアダプター サービス開発ウィザードを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ea0e33c-0d8d-4656-a6f0-3008b90f93f8
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a63953b0928915a8fea5b357722cd4e34f1b900c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-use-the-adapter-service-development-wizard-to-create-the-web-project"></a>手順 1: Web プロジェクトを作成するアダプター サービス開発ウィザードを使用します。
![4 のステップ 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 10 分  
  
 この手順では、Visual Studio を使用してプロジェクトを作成し、[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]です。 [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]アダプター、操作、およびエンドポイントの構成に関する情報を収集し、IIS に展開できる、Web プロジェクトを生成します。  
  
## <a name="prerequisites"></a>前提条件  
 ビルドおよびで説明されている Echo サンプルを配置する必要があります[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)このチュートリアルを開始する前にします。  
  
### <a name="to-start-the-adapter-service-development-wizard"></a>アダプター サービス開発ウィザードを開始するには  
  
1.  Visual Studio を起動し、**ファイル** メニューのをポイント**新規**、クリックして**Web サイト**です。  
  
2.  **新しい Web サイト** ダイアログ ボックスで、次の操作を実行します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**言語**|をクリックして**Visual c#**です。|  
    |**[テンプレート]**|をクリックして**WCF アダプタ サービス**です。|  
    |**場所**|選択**ファイル システム**、し、入力**C:\Tutorials\EchoWeb**パスとして。|  
  
3.  **[OK]**をクリックします。  
  
4.  **へようこそ ページ**、 をクリックして**次**です。  
  
### <a name="to-select-the-adapter-and-uri"></a>アダプターと URI を選択するには  
  
1.  **サービス コントラクトを生成する操作を選択して**] ページで、[ **echoAdapterBindingV2**から、**バインディングを選択**ドロップダウン ボックスの一覧、および [ ]をクリックして**構成**です。  
  
2.  **セキュリティ**のタブ、**アダプターの構成**ダイアログ ボックスで、セット**クライアント資格情報の種類**に**ユーザー名**、を設定**ユーザー名資格情報**次のようにします。  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**ユーザー名**|username|  
    |**Password**|パスワード|  
  
    > [!NOTE]
    >  ユーザー名とパスワードをここに入力は、ウィザードの手順を実行中に、アダプターへの接続にのみ使用し、ウィザードの完了後は保持されません。  
  
3.  クリックして、 **URI プロパティ**タブをクリックし、次のようにプロパティを設定します。  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**アプリケーション**|LobApplication|  
    |**EnableAuthentication**|True|  
    |**ホスト名**|lobhostname|  
    |**EchoInUpperCase**|False|  
  
    > [!NOTE]
    >  ここで選択した URI のプロパティは、作成に使用する、 \<**クライアント**>\<**エンドポイント**> web.config ファイル内の要素。  
  
4.  クリックして、**バインド プロパティ**タブです。クリックして、既定値に注意してください**OK**です。  
  
    > [!NOTE]
    >  バインディングの値の生成に使用される、 \<**バインド**>\<**echoAdapterBindingV2**> web.config ファイル内の要素。  
  
### <a name="to-select-the-contract-and-operations"></a>コントラクトと操作を選択するには  
  
1.  **サービス コントラクトを生成する操作を選択して** ページで、をクリックして**接続**です。  
  
2.  **カテゴリを選択**ツリーで、選択**メイン カテゴリ**です。 これによって、**利用可能なカテゴリと操作** ボックスの一覧です。  
  
    > [!NOTE]
    >  検索用語を入力することも、**カテゴリで検索**検索用語が含まれているすべての操作を検索するフィールドです。  
  
3.  **利用可能なカテゴリと操作**一覧で、[ **EchoGreetings** ] をクリック**追加**です。 これにより、EchoGreetings 操作に、移動、**カテゴリと操作を追加** ボックスの一覧。 ここで選択した操作は、ウィザードによって生成されたクライアント プロキシ コードをクライアント アプリケーションに公開されます。  
  
     ![コントラクトと操作の選択](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/de497b32-c820-480f-84f3-a9d0d2ded86b.gif "de497b32-c820-480f-84f3-a9d0d2ded86b")  
  
4.  **[次へ]**をクリックします。  
  
### <a name="to-configure-service-and-endpoint-behavior"></a>サービスとエンドポイントの動作を構成するには  
  
1.  **サービスとエンドポイント動作を構成する** ページで、次の値を入力**サービス動作構成**:  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**EnableMetadataExchange**|True|  
    |**IncludeExceptionDetailsinFault**|True|  
    |**名前**|customServiceBehavior|  
    |**UseServiceCertificate**|False|  
  
     これらの値が、使用、 \< **serviceBehaviors**>。  
  
2.  次の値を入力**エンドポイント動作の構成**:  
  
    |プロパティ|値|  
    |--------------|-----------|  
    |**名前**|customEndpointBehavior|  
    |**AuthenticationType**|**HTTPUsernamePassword**|  
    |**UsernameHeader**|MyUserHeader|  
    |**PasswordHeader**|MyPassHeader|  
  
     これらの値を指定するため、 **adapterSecurityBridgeType**で、<**endpointBehaviors** web.confg 内の要素。  
  
     ![エンドポイント構成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/3fd5784c-64e5-47c1-9a6f-10f12f77f726.gif "3fd5784c-64e5-47c1-9a6f-10f12f77f726")  
  
3.  **[次へ]**をクリックします。  
  
### <a name="to-configure-the-binding"></a>バインドを設定する  
  
1.  **サービス エンドポイントのバインディングとアドレスを構成する**] ページで、[、 **BindingConfiguration**内のエントリ**されたコントラクトのバインディングとアドレスを構成する**、および省略記号ボタンをクリックし、(**.**) ボタンをクリックします。  
  
2.  **のバインドのカスタマイズ**ダイアログ ボックスで、セット**モード**に**TransportWithMessageCredential**、クリックして**[ok]**です。  
  
3.  をクリックして**適用**、順にクリック**次**です。  
  
4.  **概要**ページで、コントラクトと操作をこのプロジェクトの選択を確認し、をクリックして**完了**です。 によって作成されたプロジェクト ファイルを含んでいる EchoWeb ソリューションが表示されるが、[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップで使用して、 [!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)] Web を生成する、IIS に発行されると、プロジェクトでは、ホストで開発されたエコー アダプター[チュートリアル 1: エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)IIS で処理します。 作成された Web プロジェクトでは、選択した操作にアクセスする Web サービスと WCF のクライアントを許可します。  
  
## <a name="next-steps"></a>次の手順  
 をビルドし、Web プロジェクトの配置を続行[手順 2: Web プロジェクトの配置](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: エコー アダプターを開発します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)