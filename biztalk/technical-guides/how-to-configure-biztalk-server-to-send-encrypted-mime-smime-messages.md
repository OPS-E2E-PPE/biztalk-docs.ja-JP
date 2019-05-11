---
title: 暗号化された MIME/SMIME メッセージを送信する BizTalk Server を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f67152-5f80-4040-a9d6-0819fab7fcb5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dded85a219f5a32ce83ebc4da96f0f0566bf8c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253390"
---
# <a name="how-to-configure-biztalk-server-to-send-encrypted-mimesmime-messages"></a>暗号化された MIME/SMIME メッセージを送信する BizTalk Server を構成する方法
このトピックでは、証明書を使用して暗号化された MIME/SMIME メッセージを送信する BizTalk Server を構成する方法について説明します。 以下の手順は、AS2 トランスポート経由で暗号化されたメッセージの送信の構成にも適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-configure-biztalk-server-to-send-encrypted-messages"></a>暗号化されたメッセージを送信する BizTalk Server を構成するには  
  
1. 次のように、暗号化されたメッセージを送信するためのパイプラインを作成します。  
  
   > [!NOTE]
   >  この手順に含まれるため、AS2Send および AS2EdiSend パイプラインを暗号化されたメッセージを送信するための AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この機能を提供します。  
  
   1.  送信パイプラインを作成し、パイプラインのエンコード ステージに MIME/SMIME エンコーダー パイプライン コンポーネントをドラッグします。  
  
   2.  **プロパティ**ウィンドウで、MIME/SMIME エンコーダー パイプライン コンポーネントを有効にする暗号化プロパティを構成**True**します。  
  
       > [!NOTE]  
       >  BizTalk グループにパイプラインを展開した後、BizTalk Server 管理コンソールを使用して、送信パイプライン コンポーネントのプロパティを構成することができます。  
  
   3.  送信パイプラインをビルドして配置します。  
  
2. 次のように、暗号化されたメッセージを送信するための送信ポートを構成するには。  
  
   1.  暗号化されたメッセージを受信する受信場所を含む BizTalk アプリケーションに送信パイプラインを含むに作成した BizTalk アセンブリを追加します。  
  
       > [!NOTE]  
       >  AS2Send および AS2EdiSend パイプラインが BizTalk EDI アプリケーションに含まれているために、暗号化されたメッセージを送信するための AS2 トランスポートを構成するときに、この手順は必要ではありません。  
  
   2.  BizTalk アプリケーションを前の手順で作成した送信パイプラインで送信ポートを構成します。  
  
   3.  クリックすると、送信ポートを右クリックしてインストールされている暗号化証明書を割り当てる**プロパティ**、 をクリックし、**証明書**します。 をクリックして**参照**、この送信ポートに割り当てるし をクリックしたい証明書を参照**OK**します。  
  
       > [!NOTE]  
       >  かどうか、証明書がありません、ローカル コンピューター上で、**拇印**ボックスに入力し、証明書の拇印を貼り付けますまたはクリックして**OK**。 証明書の拇印は、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進形式を持ちます。