---
title: 暗号化と証明書の署名 |Microsoft ドキュメント
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
ms.openlocfilehash: 633484a6c5599b9323bfd7798f621b27a501ce6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241690"
---
# <a name="encryption-and-signing-certificates"></a>暗号化と証明書の署名
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のセキュリティ保護は、証明書に大きく依存します。 BizTalk Server では、暗号化証明書や署名証明書を使用することで、信頼できるデータを送受信でき、処理するデータの安全性を確保できます。 暗号化とデジタル署名には、どちらも公開キー証明書と秘密キー証明書を使用します。 暗号化を使用する場合、メッセージの送信者は受信者の公開キー証明書を使用してメッセージを暗号化し、メッセージの受信者 (BizTalk Server) は秘密キーを使用してメッセージを解読します。 デジタル署名を使用する場合、メッセージの送信者は公開キー証明書を使用してメッセージに署名し、メッセージの受信者 (BizTalk Server) は送信者の公開キー証明書を使用して署名を確認します。  
  
 BizTalk Server では、受信メッセージのデジタル署名の確認と送信メッセージの暗号化に公開キー証明書を使用し、 受信メッセージの解読と送信メッセージの署名に秘密キー証明書を使用します。  
  
 BizTalk Server で使用する証明書は、BizTalk エクスプローラーおよび BizTalk Server 管理コンソールで構成できます。  
  
 デジタル証明書の詳細については、Microsoft TechNet Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508)です。  
  
> [!NOTE]
>  S/MIME (Secure Multipurpose Internet Mail Extensions) メッセージの処理中に、BizTalk Server エンジンで証明書の失効一覧 (CRL) を確認し、証明書が期限切れではないことと、ルート証明機関 (CA) にさかのぼって証明書が有効であることを確認することもできます。 確認は、パイプラインでメッセージが処理されている間に MIME/SMIME デコーダ コンポーネントで行われます。 設定する方法の詳細についての**失効リストを確認**プロパティを参照してください[- MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server で使用される証明書ストア](../core/certificate-stores-that-biztalk-server-uses.md)  
  
-   [BizTalk Server が署名されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)  
  
-   [BizTalk Server は暗号化されたメッセージを使用する証明書](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)