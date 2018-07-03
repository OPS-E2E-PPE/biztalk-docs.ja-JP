---
title: BizTalk Server で使用する証明書の署名付きメッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, signed messages
- messages, message flow [digital signatures]
- S/MIME messages
- signed messages
- digital signatures, message flow
- messages, certificates
ms.assetid: 0b521e11-73ef-424f-9e6a-4fb42dc263ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cc45411d19bc23a2985dbd60fc68bc8de58594c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979851"
---
# <a name="certificates-that-biztalk-server-uses-for-signed-messages"></a>BizTalk Server で署名付きメッセージに使用する証明書
BizTalk Server では、送信メッセージへの署名と、S/MIME (Secure Multipurpose Internet Mail Extensions) 受信メッセージに対する署名の確認がサポートされます。 送信メッセージへの署名と受信メッセージの署名の確認には、S/MIME バージョン 2 および 3 が使用されます。 同様に、BizTalk Server の構成では、パートナーへの送信メッセージが署名され暗号化されるように指定できます。  
  
- BizTalk Server では、デジタル署名の検証に SHA-1 署名アルゴリズムと MD5 署名アルゴリズムを使用できます。 送信メッセージへの署名には、SHA-1 署名アルゴリズムが使用されます。  
  
- BizTalk Server でサポートされる署名キーのキー交換システムは、RSA (Rivest-Shamir-Adleman) アルゴリズムと DSS (Digital Signature Standard) です。 BizTalk Server では、署名キーに対する AES (Advanced Encryption Standard) 交換システムの使用はサポートされません。  
  
- BizTalk Server でサポートされる署名証明書は x.509 バージョン 3 です。  
  
  次の図は、デジタル署名されたメッセージを BizTalk Server で受信し、BizTalk Server 環境内で署名を適宜使用してパートナーの ID をパーティに解決するときのメッセージ フローです。  
  
  ![署名付きメッセージを送信するときに、メッセージ フロー](../core/media/6fd1674d-5a21-4272-83ca-608d7b400de7.gif "6fd1674d-5a21-4272-83ca-608d7b400de7")  
  
  デジタル署名されたメッセージを BizTalk Server で受信するときのメッセージ フローは次のとおりです。  
  
1. パートナーから BizTalk Server にメッセージが送信されます。 パートナーは秘密キー証明書を使用してメッセージに署名します。  
  
2. 対応する BizTalk Server 受信ハンドラーでメッセージが受信されます。  
  
3. 受信パイプラインの実行中に、MIME/SMIME デコーダ パイプライン コンポーネントで、パートナーの公開キーを使用してデジタル署名が検証されます。  
  
4. パーティの解決コンポーネントが構成されている場合は、受信パイプラインのパーティの解決コンポーネントの実行中に、BizTalk Server システム内でパートナーの公開キー証明書を基にパーティが識別されます。  
  
5. 追加処理が実行されます。  
  
   次の図は、デジタル署名されたメッセージを BizTalk Server から送信するときのメッセージ フローです。  
  
   ![](../core/media/bts-bpi-sp-msgsec-outboundsigning-r2c.gif "bts_BPI_SP_MSGSEC_OutboundSigning_R2c")  
  
   デジタル署名されたメッセージを BizTalk Server からパートナーに送信するときのメッセージ フローは次のとおりです。  
  
6. 対応する BizTalk Server 送信ハンドラーからパートナーにメッセージが送信されます。  
  
7. 送信パイプラインの実行中に、MIME/SMIME エンコーダ パイプライン コンポーネントで、BizTalk Server の秘密キーを使用してメッセージが署名されます。  
  
8. パートナーが BizTalk Server からメッセージを受信します。 パートナーは BizTalk Server の公開キーを使用してデジタル署名を検証します。  
  
   BizTalk Server は、証明機関 (CA) 信頼チェーンの検証と確認することにより、証明書の証明書の有効期限が切れていない受信署名付きメッセージに関連付けられている証明書の有効性を確認します。 証明機関 (CA) の信頼チェーンの検証プロセスでは、ルート証明機関まで証明書の信頼チェーンをたどって検証が行われます。 これにより、メッセージの署名に使用された証明書が確実に、認識されている当事者からのものであることが検証されます。 この検証は、実行時、すべての署名付きメッセージに対して個別に行われます。  
  
   さらに、BizTalk Server では、証明機関が署名またはメッセージの暗号化に使用する証明書を失効していないことを確認できます。 これには、証明機関から証明書の失効一覧 (CRL) をダウンロードし、エクスプローラーを使用して CRL をインストールする必要があります。 証明書を検証する方法の詳細については、次を参照してください。 [MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server は、暗号化されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [BizTalk Server で使用される証明書ストア](../core/certificate-stores-that-biztalk-server-uses.md)   
 [暗号化および署名証明書](../core/encryption-and-signing-certificates.md)   
 [署名付きメッセージの送受信](../core/sending-and-receiving-signed-messages.md)