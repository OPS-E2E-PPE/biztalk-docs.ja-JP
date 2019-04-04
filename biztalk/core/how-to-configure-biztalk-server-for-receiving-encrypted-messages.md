---
title: 暗号化されたメッセージを受信するための BizTalk Server を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd1e7e4c-f80c-468e-aa86-7c18406feead
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765c47755e0d170473d92e755eba11e10a4dc3d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023576"
---
# <a name="how-to-configure-biztalk-server-for-receiving-encrypted-messages"></a>暗号化されたメッセージを受信するための BizTalk Server の構成方法
次の手順では、暗号化されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成するときの手順について説明します。  
  
-   暗号化されたメッセージを受信するためのパイプラインを作成するには  
  
-   暗号化されたメッセージを受信するための受信場所を構成するには  
  
## <a name="prerequisites"></a>前提条件  
 構成する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]暗号化されたメッセージを受信するためで手順を実行する必要があります[メッセージの暗号化の証明書をインストールする方法](../core/how-to-install-the-certificates-for-encrypted-messages.md)します。  
  
### <a name="to-create-a-pipeline-to-receive-encrypted-messages"></a>暗号化されたメッセージを受信するためのパイプラインを作成するには  
  
1. Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。  
  
   1.  **ファイル** メニューのをクリックして**新しい項目の追加**します。  
  
   2.  **新しい項目の追加** ダイアログ ボックスで、BizTalk プロジェクトの項目を展開し、**パイプライン ファイル**、 をクリックし、**受信パイプライン**テンプレート。  
  
   3.  **名前**フィールドに、パイプラインの名前を入力します。  
  
   4.  **[追加]** をクリックします。  
  
        新しいパイプラインがソリューション エクスプローラーに表示されます。  
  
2. MIME/SMIME デコーダー パイプライン コンポーネントを受信パイプラインのデコード ステージにドラッグします。  
  
    ![MIME&#47;SMIME デコーダー パイプライン コンポーネント](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")  
  
   -   MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成、**プロパティ**ウィンドウ。 MIME/SMIME デコーダーの詳細については、[MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)を参照してください。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。 BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。 詳細については、[受信場所のインスタンスごとのパイプライン プロパティを構成する方法](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)を参照してください。  
   > 
   > [!NOTE]
   >  MIME/SMIME デコーダー パイプライン コンポーネントは、解読とデジタル署名の検証の両方を実行します (両方の機能を実行するように構成されている場合)。 したがって、暗号化および署名されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ受信パイプラインを使用できます。 つまり、解読用とデジタル署名の検証用に異なるパイプラインを作成する必要はありません。  
  
3. 受信パイプラインをビルドして配置します。  
  
### <a name="to-configure-the-receive-location-for-receiving-encrypted-messages"></a>暗号化されたメッセージを受信するための受信場所を構成するには  
  
1.  前の手順で作成した BizTalk アセンブリを、暗号化されたメッセージの受信場所を含む BizTalk アプリケーションに追加します。 BizTalk アセンブリを追加する方法の詳細については、[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)を参照してください。  
  
2.  前の手順で作成した受信パイプラインを使用して、BizTalk アプリケーションの受信場所を構成します。 構成する方法については、受信場所を参照してください[受信場所のプロパティを編集する方法](../core/how-to-edit-the-properties-of-a-receive-location.md)します。  
  
3.  手順でインストールされている解読証明書の受信場所の受信ハンドラーとして使用されるホストを構成するには"暗号化されたメッセージを受信するための BizTalk ホストを構成する"で[暗号化の証明書をインストールする方法メッセージ](../core/how-to-install-the-certificates-for-encrypted-messages.md)します。 詳細についてはホストのプロパティを構成するを参照してください方法[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server は、暗号化されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [暗号化されたメッセージを送信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)   
 [暗号化されたメッセージの送受信](../core/sending-and-receiving-encrypted-messages.md)