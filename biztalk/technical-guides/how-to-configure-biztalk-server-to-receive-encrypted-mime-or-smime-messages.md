---
title: 暗号化された MIME または SMIME メッセージを受信する BizTalk Server を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d72002c8-6bd8-458f-8149-1c0c4cbbb682
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b785e85f4d53feda47f4ebf4bf0ab34c56b830d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242624"
---
# <a name="how-to-configure-biztalk-server-to-receive-encrypted-mime-or-smime-messages"></a>暗号化された MIME または SMIME メッセージを受信する BizTalk Server を構成する方法
このトピックでは、構成する方法を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]証明書を使用して暗号化された MIME/SMIME メッセージを受信します。 以下の手順は、AS2 トランスポート経由の暗号化されたメッセージの受信の構成にも適用されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行する必要がありますがログオンしてのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
### <a name="to-configure-biztalk-server-to-receive-encrypted-messages"></a>暗号化されたメッセージを受信する BizTalk Server を構成するには  
  
1. 次のように、暗号化されたメッセージを受信するためのパイプラインを作成します。  
  
   > [!NOTE]
   >  BizTalk Server に含まれている AS2Receive と AS2EdiReceive パイプラインは、この機能を提供するために、暗号化されたメッセージを受信するための AS2 トランスポートを構成するときに、この手順は必要ではありません。  
   > 
   > [!NOTE]
   >  MIME/SMIME デコーダー パイプライン コンポーネントは、解読とデジタル署名の検証の両方を実行します (両方の機能を実行するように構成されている場合)。 したがって、暗号化および署名されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ受信パイプラインを使用できます。 つまり、解読用とデジタル署名の検証用に異なるパイプラインを作成する必要はありません。  
  
   1. 受信パイプラインを作成し、パイプラインのデコード ステージに MIME/SMIME デコーダー パイプライン コンポーネントをドラッグします。  
  
   2. **プロパティ**ウィンドウで、MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成します。  
  
      > [!NOTE]
      >  MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成するには、失効リストを確認プロパティを送信者のに送信されるメッセージの署名に使用される証明書の証明書失効リストを確認したい場合はTrueに設定が含まれます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. このオプションを無効にすると、コンポーネントのパフォーマンスが向上します。 証明書に関連付けられている証明書失効リストは、適切な証明書サービスの Web サイトからダウンロードされます。 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]リモートの Web サイトのパイプラインでメッセージが失敗に接続できません。  
      > 
      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。 BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。  
  
   3. 受信パイプラインをビルドして配置します。  
  
2. 次のように、暗号化されたメッセージを受信するための受信場所を構成します。  
  
   1. 暗号化されたメッセージを受信する受信場所を含む BizTalk アプリケーションに受信パイプラインを含むに作成した BizTalk アセンブリを追加します。  
  
      > [!NOTE]
      >  この手順は、AS2Receive と AS2EdiReceive パイプラインが BizTalk EDI アプリケーションに含まれているために、暗号化されたメッセージを受信するための AS2 トランスポートを構成するときに必要ない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
   2. BizTalk アプリケーションを前の手順で作成した受信パイプラインで受信場所を構成します。  
  
3. 次のように復号化証明書が、受信場所の受信ハンドラーとして使用するホストを構成します。  
  
   1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、BizTalk は、暗号化されたメッセージの受信ハンドラーでホストされている、クリックして右クリック**プロパティ**します。  
  
      > [!NOTE]
      >  この手順は、AS2 トランスポートで使用できるは適用されません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 BizTalk MIME デコーダー、AS2 デコーダーではないが適用されます。 AS2 デコーダーでは、メッセージ内の証明書情報に基づく証明書を決定します。  
  
   2. **ホストのプロパティ**ダイアログ ボックスで、をクリックして**証明書**、順にクリックします**参照**します。  
  
      > [!NOTE]
      >  上記の手順では、構成することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境のためだけである特定のホストは受信し、特定のメッセージを処理します。 メッセージのデコードおよび解読を行うに使用する証明書の拇印を持つホストを構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースでは、そのホストのアプリケーション プロパティを作成します。 受信したメッセージをセキュリティで保護し、この拇印を使用して復号化されたが、ルーティングのみ、この拇印で構成されている他のホストにします。  
  
   3. **証明書の選択**ダイアログ ボックスがインストールした解読証明書を選択し、すべてのダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [MIME またはメッセージの SMIME 証明書の構成](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)