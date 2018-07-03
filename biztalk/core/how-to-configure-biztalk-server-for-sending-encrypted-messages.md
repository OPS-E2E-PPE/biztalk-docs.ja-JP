---
title: 暗号化されたメッセージを送信するための BizTalk Server を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb751d7c-49cd-46f0-9630-254cf06c497e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49f7388e9f6b8e56397a3b6efdf466aec3383746
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023904"
---
# <a name="how-to-configure-biztalk-server-for-sending-encrypted-messages"></a>暗号化されたメッセージを送信するための BizTalk Server を構成する方法
暗号化されたメッセージを送信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する手順を次に示します。  
  
-   暗号化されたメッセージを送信するためのパイプラインを作成するには  
  
-   暗号化されたメッセージを送信するための送信ポートを構成するには  
  
## <a name="prerequisites"></a>前提条件  
 構成する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]暗号化されたメッセージを送信するためで手順を実行する必要があります[メッセージの暗号化の証明書をインストールする方法](../core/how-to-install-the-certificates-for-encrypted-messages.md)します。  
  
### <a name="to-create-a-pipeline-to-send-encrypted-messages"></a>暗号化されたメッセージを送信するためのパイプラインを作成するには  
  
1. Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。  
  
   1.  **ファイル** メニューのをクリックして**新しい項目の追加**します。  
  
   2.  **新しい項目の追加** ダイアログ ボックスで、BizTalk プロジェクトの項目を展開し、**パイプライン ファイル**、 をクリックし、**送信パイプライン**テンプレート。  
  
   3.  **名前**フィールドに、パイプラインの名前を入力します。  
  
   4.  **[追加]** をクリックします。  
  
        新しいパイプラインがソリューション エクスプローラーに表示されます。  
  
2. MIME/SMIME エンコーダー パイプライン コンポーネントを受信パイプラインの [エンコード] ステージにドラッグします。  
  
    ![MIME&#47;SMIME エンコーダー パイプライン コンポーネント](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")  
  
   -   MIME/SMIME エンコーダー パイプライン コンポーネントの構成プロパティ ウィンドウで**暗号化を有効にする**プロパティを`True`します。 詳細については、**暗号化を有効にする**プロパティを参照してください[MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)します。  
  
   > [!NOTE]
   >  BizTalk グループにパイプラインを展開した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して送信パイプライン コンポーネントのプロパティを構成できます。 詳細については、次を参照してください。[送信ポートのインスタンスごとのパイプライン プロパティを構成する方法](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)します。  
   > 
   > [!NOTE]
   >  MIME/SMIME エンコーダー パイプライン コンポーネントは、暗号化とデジタル署名の両方を実行します (両方の機能を実行するように構成されている場合)。 したがって、暗号化および署名されたメッセージを送信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ送信パイプラインを使用できます。 つまり、暗号化用とデジタル署名用に異なるパイプラインを作成する必要はありません。  
  
3. 送信パイプラインをビルドして配置します。  
  
### <a name="to-configure-the-send-port-for-sending-encrypted-messages"></a>暗号化されたメッセージを送信するための送信ポートを構成するには  
  
1.  前の手順で作成した BizTalk アセンブリを、暗号化されたメッセージを送信する送信ポートを含む BizTalk アプリケーションに追加します。 BizTalk アセンブリを追加する方法の詳細については、次を参照してください。[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。  
  
2.  前の手順で作成した送信パイプラインを備えた、BizTalk アプリケーションに送信ポートを構成しにインストールされている暗号化証明書を割り当てます[メッセージの暗号化の証明書をインストールする方法](../core/how-to-install-the-certificates-for-encrypted-messages.md). 送信ポートを構成する方法の詳細については、次を参照してください。[送信ポートに証明書を割り当てる方法](../core/how-to-assign-a-certificate-to-a-send-port.md)します。  
  
## <a name="see-also"></a>参照  
 [暗号化されたメッセージを受信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)   
 [BizTalk Server は、暗号化されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [暗号化されたメッセージの送受信](../core/sending-and-receiving-encrypted-messages.md)