---
title: 暗号化と証明書の署名 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, security
- security, certificates
- security, messages
- certificates, encryption
- encryption certificates, messages
- messages, encryption
- messages, certificates
- security, encryption
ms.assetid: 3c3f9de5-4156-4133-8d5e-c30b142b6d61
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee36208b232609c5a73ede9a933f692a0681827f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349548"
---
# <a name="encryption-and-signing-certificates"></a>暗号化および署名証明書
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は、証明書のセキュリティに大きく依存します。 暗号化とデジタル署名の証明書を使用して BizTalk Server はことができます、信頼できるし、処理するデータが安全であることを確認に役立つデータを送受信します。 暗号化とデジタル署名の両方の公開キー証明書と秘密キー証明書があります。 暗号化は、メッセージの送信者は受信者の公開キー証明書を使用して、(BizTalk Server) のメッセージの受信者、メッセージの解読にその秘密キーを使用しますが、メッセージを暗号化します。 デジタル署名は、メッセージの送信者が、メッセージの署名に秘密キー証明書を使用し、(BizTalk Server) のメッセージの受信者が送信者の公開キー証明書を使用して署名を検証します。  
  
 BizTalk Server では、公開キー証明書を使用して、受信メッセージの送信メッセージの暗号化とデジタル署名を検証します。 BizTalk Server では、受信メッセージの解読と送信メッセージの署名を秘密キー証明書を使用します。  
  
 BizTalk エクスプ ローラーで、BizTalk 管理コンソールでは、BizTalk Server を使用して証明書を構成します。  
  
 デジタル証明書の詳細については、Microsoft TechNet Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508)します。  
  
> [!NOTE]
>  Secure Multipurpose Internet Mail Extensions (S/MIME) メッセージを処理中には、証明書の有効期限が切れていないことと、ルートまで信頼されていることを確認する証明書失効リスト (CRL) を確認してください。 BizTalk Server エンジンを選択できます。証明書機関 (CA)。 この検証では、パイプラインは、MIME/SMIME デコーダー コンポーネントで、メッセージの処理中に発生します。 設定する方法の詳細についての**失効リストを確認**プロパティを参照してください[MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server で使用される証明書ストア](../core/certificate-stores-that-biztalk-server-uses.md)  
  
-   [BizTalk Server で署名付きメッセージに使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)  
  
-   [BizTalk Server で暗号化されたメッセージに使用する証明書](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)