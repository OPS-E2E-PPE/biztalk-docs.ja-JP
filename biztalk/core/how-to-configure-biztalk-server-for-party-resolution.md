---
title: BizTalk Server パーティの解決を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ac330b9-3498-4c98-a6e8-d2c02cd641dd
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d6fc4f0f0dc61b111060aebb26b8dccfc32ec15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991059"
---
# <a name="how-to-configure-biztalk-server-for-party-resolution"></a>パーティの解決用に BizTalk Server を構成する方法
次の手順では、パーティの解決用に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成するときの手順について説明します。  
  
-   署名付きメッセージを受信するための証明書を証明書ストアにインストールするには  
  
-   パートナーを表すパーティを作成するには  
  
-   証明書を使用してパーティの解決用のパイプラインを作成するには  
  
-   証明書を使用してパーティの解決の受信場所を構成するには  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a>署名付きメッセージを受信するための証明書を証明書ストアにインストールするには  
  
1. パートナー A は、証明機関 (CA) にデジタル署名用の公開キーと秘密キーのペアを要求します。  
  
2. パートナー A は、ユーザーにデジタル署名用の公開キーを送信します。  
  
3. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、パートナー A からのメッセージを受信するハンドラーを実行中のホスト インスタンスを含むサーバーにログオンします。パートナー A の公開キー証明書をインストールして、"その他のユーザー" ストアの署名を検証します。 次の図に、証明書をインストールする証明書ストアを示します。  
  
    ![セキュリティで保護されたメッセージを受信するために必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4. パートナー A で、適切なストアでメッセージに署名するためにパートナー A の秘密キー証明書をインストールします  (パートナー A が使用されている場合[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、または[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]に送信されるメッセージに署名するアカウントの個人用ストアに秘密キーをインストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。  
  
   > [!NOTE]
   >  この手順は、"署名付きメッセージを受信する証明書ストアに証明書のインストール"する手順とまったく同じで[デジタル署名用証明書をインストールする方法](../core/how-to-install-the-certificates-for-digital-signatures.md)します。  
  
### <a name="to-create-a-party-to-represent-your-partner"></a>パートナーを表すパーティを作成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、パーティをパートナー A. の作成パーティを作成する方法の詳細については、[パーティを作成する方法](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)を参照してください。  
  
2. **証明書**プロパティは、パートナー A.、このパーティを識別するために使用する証明書の署名の公開キーを選択します。  
  
### <a name="to-create-a-pipeline-for-party-resolution-using-certificates"></a>証明書を使用してパーティの解決用のパイプラインを作成するには  
  
1. Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。  
  
   1.  **ファイル** メニューのをクリックして**新しい項目の追加**します。  
  
   2.  **新しい項目の追加** ダイアログ ボックスで、BizTalk プロジェクトの項目を展開し、**パイプライン ファイル**、 をクリックし、**受信パイプライン**テンプレート。  
  
   3.  **名前**フィールドに、パイプラインの名前を入力します。  
  
   4.  **[追加]** をクリックします。  
  
        新しいパイプラインがソリューション エクスプローラーに表示されます。  
  
2. MIME/SMIME デコーダー パイプライン コンポーネントをドラッグして、**デコード**受信パイプラインのステージ。  
  
    ![MIME&#47;SMIME デコーダー パイプライン コンポーネント](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")  
  
   -   MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成、**プロパティ**ウィンドウ。 MIME/SMIME デコーダーの詳細については、[MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)を参照してください。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。 BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。 詳細については、[受信場所のインスタンスごとのパイプライン プロパティを構成する方法](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)を参照してください。  
   > 
   > [!NOTE]
   >  MIME/SMIME デコーダー パイプライン コンポーネントは、解読とデジタル署名の検証の両方を実行します (両方の機能を実行するように構成されている場合)。 したがって、暗号化および署名されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ受信パイプラインを使用できます。 つまり、解読用とデジタル署名の検証用に異なるパイプラインを作成する必要はありません。  
  
3. パーティの解決パイプライン コンポーネントをドラッグして、**パーティの解決**受信パイプラインのステージ。 パーティの解決パイプライン コンポーネントの詳細については、[パーティの解決パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-party-resolution-pipeline-component.md)を参照してください。  
  
   > [!NOTE]
   >  新しい受信パイプラインを作成する代わりに、既定の XMLReceive パイプラインを使用することもできます。 XMLReceive パイプラインは、証明書サブジェクトをパーティ ID を解決するパーティの解決コンポーネントを実行します。 XMLReceive パイプラインが空のデコード ステージで、そのための暗号化されたメッセージの受信やデジタル署名の検証を使用することはできないことに注意してください。  
  
   -   [プロパティ] ウィンドウで、パーティの解決パイプラインのプロパティを構成する**証明書によるパーティの解決**に`True`します。  
  
4. 受信パイプラインをビルドして配置します。  
  
### <a name="to-configure-the-receive-location-for-party-resolution-using-certificates"></a>証明書を使用してパーティの解決の受信場所を構成するには  
  
1.  前の手順で作成した BizTalk アセンブリを、署名付きメッセージの受信場所を含む BizTalk アプリケーションに追加します。 BizTalk アセンブリを追加する方法の詳細については、[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)を参照してください。  
  
2.  前の手順で作成した受信パイプラインを使用して、BizTalk アプリケーションの受信場所を構成します。 構成する方法については、受信場所を参照してください[受信場所のプロパティを編集する方法](../core/how-to-edit-the-properties-of-a-receive-location.md)します。  
  
## <a name="see-also"></a>参照  
 [署名付きメッセージを受信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [BizTalk Server は、署名付きメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [受信メッセージの認証](../core/inbound-message-authentication.md)   
 [パーティの解決での証明書の使用](../core/using-certificates-for-party-resolution.md)