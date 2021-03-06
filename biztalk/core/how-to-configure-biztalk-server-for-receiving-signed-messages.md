---
title: 署名付きメッセージを受信するための BizTalk Server を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48479532-24a9-41d9-a3b8-2a23f4e76457
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c05459fbf88882537ea83c6d7697d5707beb6b19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341569"
---
# <a name="how-to-configure-biztalk-server-for-receiving-signed-messages"></a>署名付きメッセージを受信するための BizTalk Server の構成方法
次の手順では、暗号化されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成するときの手順について説明します。  
  
-   署名付きメッセージを受信するためのパイプラインを作成するには  
  
-   署名付きメッセージを受信するための受信場所を構成するには  
  
## <a name="prerequisites"></a>前提条件  
 構成する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]署名付きメッセージを受信するためで手順を実行する必要があります[デジタル署名用証明書をインストールする方法](../core/how-to-install-the-certificates-for-digital-signatures.md)します。  
  
### <a name="to-create-a-pipeline-to-receive-signed-messages"></a>署名付きメッセージを受信するためのパイプラインを作成するには  
  
1. Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。  
  
   1.  **ファイル** メニューのをクリックして**新しい項目の追加**します。  
  
   2.  **新しい項目の追加** ダイアログ ボックスで、BizTalk プロジェクトの項目を展開し、**パイプライン ファイル**、 をクリックし、**受信パイプライン**テンプレート。  
  
   3.  **名前**フィールドに、パイプラインの名前を入力します。  
  
   4.  **[追加]** をクリックします。  
  
        新しいパイプラインがソリューション エクスプローラーに表示されます。  
  
2. MIME/SMIME デコーダー パイプライン コンポーネントをドラッグして、**デコード**受信パイプラインのステージ。  
  
    ![MIME&#47;SMIME デコーダー パイプライン コンポーネント](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")  
  
   -   MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成、**プロパティ**ウィンドウ。 MIME/SMIME デコーダーの詳細については、次を参照してください。 [MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)します。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。 BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。 詳細については、次を参照してください。[受信場所のインスタンスごとのパイプライン プロパティを構成する方法](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)します。  
   > 
   > [!NOTE]
   >  MIME/SMIME デコーダー パイプライン コンポーネントは、解読とデジタル署名の検証の両方を実行します (両方の機能を実行するように構成されている場合)。 したがって、暗号化および署名されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ受信パイプラインを使用できます。 つまり、解読用とデジタル署名の検証用に異なるパイプラインを作成する必要はありません。  
  
3. 受信パイプラインをビルドして配置します。  
  
### <a name="to-configure-the-receive-location-for-receiving-signed-messages"></a>署名付きメッセージを受信するための受信場所を構成するには  
  
1.  前の手順で作成した BizTalk アセンブリを、署名付きメッセージの受信場所を含む BizTalk アプリケーションに追加します。 BizTalk アセンブリを追加する方法の詳細については、次を参照してください。[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。  
  
2.  前の手順で作成した受信パイプラインを使用して、BizTalk アプリケーションの受信場所を構成します。 構成する方法については、受信場所を参照してください[受信場所のプロパティを編集する方法](../core/how-to-edit-the-properties-of-a-receive-location.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server は、署名付きメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [署名付きメッセージを送信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)   
 [メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)   
 [署名付きメッセージの送受信](../core/sending-and-receiving-signed-messages.md)