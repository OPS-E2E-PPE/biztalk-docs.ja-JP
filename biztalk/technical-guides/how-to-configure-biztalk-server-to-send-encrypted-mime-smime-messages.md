---
title: "暗号化された MIME/SMIME メッセージを送信する BizTalk Server を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14f67152-5f80-4040-a9d6-0819fab7fcb5
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c83b5f28ac3716376aa93cff22f933363825615e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-to-send-encrypted-mimesmime-messages"></a>暗号化された MIME/SMIME メッセージを送信する BizTalk Server を構成する方法
このトピックでは、暗号化された MIME/SMIME メッセージを送信する証明書を使用する BizTalk Server を構成する方法について説明します。 以下の手順は、AS2 トランスポート経由で暗号化されたメッセージの送信の構成にも適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-configure-biztalk-server-to-send-encrypted-messages"></a>暗号化されたメッセージを送信する BizTalk Server を構成するには  
  
1.  次のように、暗号化されたメッセージを送信するためのパイプラインを作成します。  
  
    > [!NOTE]  
    >  この手順に含まれるため、AS2Send および AS2EdiSend パイプラインを暗号化されたメッセージを送信するための AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この機能を提供します。  
  
    1.  送信パイプラインを作成し、パイプラインのエンコード ステージに MIME/SMIME エンコーダー パイプライン コンポーネントをドラッグします。  
  
    2.  **プロパティ** ウィンドウで、MIME/SMIME エンコーダー パイプライン コンポーネントを有効にする暗号化プロパティを構成**True**です。  
  
        > [!NOTE]  
        >  BizTalk グループにパイプラインを展開した後、BizTalk Server 管理コンソールを使用して送信パイプライン コンポーネントのプロパティを構成できます。  
  
    3.  送信パイプラインをビルドして配置します。  
  
2.  次のように、暗号化されたメッセージを送信するための送信ポートを構成します。  
  
    1.  暗号化されたメッセージを受信する受信場所を含む BizTalk アプリケーションに送信パイプラインを含むに作成した BizTalk アセンブリを追加します。  
  
        > [!NOTE]  
        >  AS2Send および AS2EdiSend パイプラインが BizTalk EDI アプリケーションに含まれているために、暗号化されたメッセージを送信するための AS2 トランスポートを構成するときに、この手順は必要ではありません。  
  
    2.  前の手順で作成した送信パイプラインを持つ BizTalk アプリケーションでの送信ポートを構成します。  
  
    3.  クリックすると、送信ポートを右クリックしてインストールされている暗号化証明書を割り当てる**プロパティ**、クリックして**証明書**です。 をクリックして**参照**、この送信ポートに割り当てるし、をクリックする証明書を参照**OK**です。  
  
        > [!NOTE]  
        >  かどうか、証明書が、ローカル コンピューター上にありません、**拇印**ボックスに入力し、証明書の拇印を貼り付け、またはをクリックして**OK**です。 証明書の拇印の形式は、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH です。H は 16 進数です。