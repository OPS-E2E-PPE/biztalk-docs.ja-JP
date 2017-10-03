---
title: "署名付きメッセージを送信するための BizTalk Server を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be86fbb3-de80-4d9f-bcf0-c61347704229
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef71f5c11d6c1a000369644b822aa9f4d4ef792
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-for-sending-signed-messages"></a>署名付きメッセージを送信するための BizTalk Server の構成方法
署名付きメッセージを送信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する手順を次に示します。  
  
-   署名付きメッセージを送信するためのパイプラインを作成するには  
  
-   署名付きメッセージを送信するための送信ポートを構成するには  
  
## <a name="prerequisites"></a>前提条件  
 構成する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s 署名付きメッセージを送信するための手順を実行する必要があります[デジタル署名の証明書をインストールする方法](../core/how-to-install-the-certificates-for-digital-signatures.md)です。  
  
### <a name="to-create-a-pipeline-to-send-signed-messages"></a>署名付きメッセージを送信するためのパイプラインを作成するには  
  
1.  Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。  
  
    1.  **ファイル** メニューのをクリックして**新しい項目の追加**です。  
  
    2.  **新しい項目の追加** ダイアログ ボックスで BizTalk プロジェクトの項目を展開し、をクリックして**パイプライン ファイル**、をクリックし、**送信パイプライン**テンプレート。  
  
    3.  **名前**フィールドに、パイプラインの名前を入力します。  
  
    4.  **[追加]**をクリックします。  
  
         新しいパイプラインがソリューション エクスプローラーに表示されます。  
  
2.  MIME/SMIME エンコーダー パイプライン コンポーネントを受信パイプラインの [エンコード] ステージにドラッグします。  
  
     ![MIME & #47。SMIME エンコーダー パイプライン コンポーネント](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")  
  
3.  [プロパティ] ウィンドウで、MIME/SMIME エンコーダー パイプライン コンポーネントを構成する**署名の種類**プロパティを**ClearSign**または**BlobSign**です。 詳細については、**暗号化を有効にする**プロパティを参照してください[- MIME/SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)です。  
  
    > [!IMPORTANT]
    >  暗号化を使用しても場合のみ選択**BlobSign**です。  
  
    > [!NOTE]
    >  BizTalk グループにパイプラインを展開した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して送信パイプライン コンポーネントのプロパティを構成できます。 詳細については、次を参照してください。[送信ポートのインスタンスごとのパイプライン プロパティを構成する方法](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)です。  
  
    > [!NOTE]
    >  MIME/SMIME エンコーダー パイプライン コンポーネントは、暗号化とデジタル署名の両方を実行します (両方の機能を実行するように構成されている場合)。 したがって、暗号化および署名されたメッセージを送信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ送信パイプラインを使用できます。 つまり、暗号化用とデジタル署名用に異なるパイプラインを作成する必要はありません。  
  
4.  送信パイプラインをビルドして配置します。  
  
### <a name="to-configure-the-send-port-for-sending-signed-messages"></a>署名付きメッセージを送信するための送信ポートを構成するには  
  
1.  前の手順で作成した BizTalk アセンブリを、送信する署名付きメッセージの受信場所を含む BizTalk アプリケーションに追加します。 BizTalk アセンブリを追加する方法の詳細については、次を参照してください。 [BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。  
  
2.  前の手順で作成した送信パイプラインを使用して、BizTalk アプリケーションの送信ポートを構成します。 送信ポートを構成する方法の詳細については、次を参照してください。[の作成および構成する送信ポート](../core/creating-and-configuring-send-ports.md)です。  
  
3.  BizTalk グループ、署名証明書を構成でインストールした[デジタル署名の証明書をインストールする方法](../core/how-to-install-the-certificates-for-digital-signatures.md)です。 詳細については、BizTalk グループを構成する方法[グループのプロパティを変更する方法](../core/how-to-modify-group-properties.md)です。  
  
## <a name="see-also"></a>参照  
 [署名付きメッセージを受信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [BizTalk Server が署名されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [署名付きメッセージを送受信します。](../core/sending-and-receiving-signed-messages.md)