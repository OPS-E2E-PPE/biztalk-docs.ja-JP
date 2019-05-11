---
title: 署名付きメッセージを送信するための BizTalk Server を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be86fbb3-de80-4d9f-bcf0-c61347704229
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fca2bc8c66b6338bf65c0d6ebdb5c977942779b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341520"
---
# <a name="how-to-configure-biztalk-server-for-sending-signed-messages"></a>署名付きメッセージを送信するための BizTalk Server の構成方法
署名付きメッセージを送信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する手順を次に示します。  
  
-   署名付きメッセージを送信するためのパイプラインを作成するには  
  
-   署名付きメッセージを送信するための送信ポートを構成するには  
  
## <a name="prerequisites"></a>前提条件  
 構成する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]署名付きメッセージを送信するためで手順を実行する必要があります[デジタル署名用証明書をインストールする方法](../core/how-to-install-the-certificates-for-digital-signatures.md)します。  
  
### <a name="to-create-a-pipeline-to-send-signed-messages"></a>署名付きメッセージを送信するためのパイプラインを作成するには  
  
1. Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。  
  
   1.  **ファイル** メニューのをクリックして**新しい項目の追加**します。  
  
   2.  **新しい項目の追加** ダイアログ ボックスで、BizTalk プロジェクトの項目を展開し、**パイプライン ファイル**、 をクリックし、**送信パイプライン**テンプレート。  
  
   3.  **名前**フィールドに、パイプラインの名前を入力します。  
  
   4.  **[追加]** をクリックします。  
  
        新しいパイプラインがソリューション エクスプローラーに表示されます。  
  
2. MIME/SMIME エンコーダー パイプライン コンポーネントを受信パイプラインの [エンコード] ステージにドラッグします。  
  
    ![MIME&#47;SMIME エンコーダー パイプライン コンポーネント](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")  
  
3. MIME/SMIME エンコーダー パイプライン コンポーネントの構成プロパティ ウィンドウで**署名の種類**プロパティを**ClearSign**または**blobsign**します。 詳細については、**暗号化を有効にする**プロパティを参照してください[MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)します。  
  
   > [!IMPORTANT]
   >  選択できるだけの暗号化を使用しても場合 **[blobsign]** します。  
   > 
   > [!NOTE]
   >  BizTalk グループにパイプラインを展開した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して送信パイプライン コンポーネントのプロパティを構成できます。 詳細については、次を参照してください。[送信ポートのインスタンスごとのパイプライン プロパティを構成する方法](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)します。  
   > 
   > [!NOTE]
   >  MIME/SMIME エンコーダー パイプライン コンポーネントは、暗号化とデジタル署名の両方を実行します (両方の機能を実行するように構成されている場合)。 したがって、暗号化および署名されたメッセージを送信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ送信パイプラインを使用できます。 つまり、暗号化用とデジタル署名用に異なるパイプラインを作成する必要はありません。  
  
4. 送信パイプラインをビルドして配置します。  
  
### <a name="to-configure-the-send-port-for-sending-signed-messages"></a>署名付きメッセージを送信するための送信ポートを構成するには  
  
1.  前の手順で作成した BizTalk アセンブリを、送信する署名付きメッセージの受信場所を含む BizTalk アプリケーションに追加します。 BizTalk アセンブリを追加する方法の詳細については、次を参照してください。[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。  
  
2.  前の手順で作成した送信パイプラインを使用して、BizTalk アプリケーションの送信ポートを構成します。 送信ポートを構成する方法の詳細については、次を参照してください。[構成する送信ポートの作成と](../core/creating-and-configuring-send-ports.md)します。  
  
3.  BizTalk グループの構成でインストールした署名証明書で[デジタル署名用証明書をインストールする方法](../core/how-to-install-the-certificates-for-digital-signatures.md)します。 詳細については BizTalk グループを構成する方法[グループ プロパティを変更する方法](../core/how-to-modify-group-properties.md)します。  
  
## <a name="see-also"></a>参照  
 [署名付きメッセージを受信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [BizTalk Server は、署名付きメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [署名付きメッセージの送受信](../core/sending-and-receiving-signed-messages.md)