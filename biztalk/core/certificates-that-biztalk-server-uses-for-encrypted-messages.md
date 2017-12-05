---
title: "暗号化されたメッセージを BizTalk Server で使用される証明書 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message flow [encrypted messages]
- encrypted messages
- messages, encryption
ms.assetid: 44b06488-4ecd-436d-af3d-b95e285ecb3e
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f2dbd51506da7b505f66b3001b8bdc6fa0a58ac
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="certificates-that-biztalk-server-uses-for-encrypted-messages"></a>BizTalk Server で暗号化されたメッセージに使用する証明書
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、S/MIME (Secure Multipurpose Internet Mail Extensions) を使用した公開キーによる送信メッセージの暗号化と、受信メッセージの解読がサポートされます。 送信メッセージの暗号化には S/MIME バージョン 3 が使用され、受信メッセージの解読には S/MIME バージョン 2 と 3 が使用されます。  
  
-   BizTalk Server では、RSA および Diffie Hellman 暗号化証明書がサポートされています。  
  
-   また、DES (Data Encryption Standard)、3DES、および RC2 暗号化アルゴリズムがサポートされています。  
  
 暗号化されたメッセージが BizTalk Server で受信されたときのメッセージ フローを次に示します。  
  
 ![暗号化されたメッセージを受信するときに、メッセージ フロー](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")  
  
 暗号化されたメッセージが BizTalk Server で受信されたときのメッセージ フローは次のとおりです。  
  
1.  パートナーから BizTalk Server にメッセージが送信されます。 パートナーは BizTalk Server の公開キーを使用してメッセージを暗号化します。  
  
2.  対応する BizTalk Server 受信ハンドラーでメッセージが受信されます。  
  
3.  受信パイプラインの実行中に、MIME/SMIME デコーダー パイプライン コンポーネントで、BizTalk Server の秘密キーを使用してメッセージが解読されます。  
  
    > [!NOTE]
    >  IIS 7.0 コンピューターで正常にパイプラインの復号化は、IIS アプリケーション プールのアカウントおよび受信ハンドラーに関連付けられているホスト インスタンスによって使用されるアカウントは、同じであると、このアカウントがのメンバーであることを確認、 \<machineName\>\IIS_WPG グループ。 IIS の設定の詳細については、プロセス IIS 7.0 は、「id [IIS アクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)です。 これらのプロセスは同じアカウントで実行する必要があります。これは、アカウント プロファイルが読み込まれ、それに続いてパイプラインで解読を実行するのに必要なレジストリ キーが読み込まれるようにするためです。 IIS 7.0 では、パフォーマンス上の理由のため、関連する w3wp.exe プロセスの開始時にアカウント プロファイルが読み込まれません。したがって、BizTalk がアカウント プロファイルとレジストリ キーを読み込むように BizTalk ホスト インスタンスを同じアカウントで構成する必要があります。  
  
4.  追加処理が実行されます。  
  
 次の図に、暗号化されたメッセージが BizTalk Server から送信されたときのメッセージ フローを示します。  
  
 ![暗号化されたメッセージを送信するときに、メッセージ フロー](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")  
  
 暗号化されたメッセージが BizTalk Server からパートナーに送信されたときのメッセージ フローは次のとおりです。  
  
1.  対応する BizTalk Server 送信ハンドラーからパートナーにメッセージが送信されます。  
  
2.  送信パイプラインの実行中に、MIME/SMIME エンコーダー パイプライン コンポーネントで、パートナーの公開キーを使用してメッセージが暗号化されます。  
  
3.  パートナーが BizTalk Server からメッセージを受信します。 パートナーは秘密キーを使用してメッセージを解読します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が署名されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [BizTalk Server で使用される証明書ストア](../core/certificate-stores-that-biztalk-server-uses.md)   
 [暗号化と証明書の署名](../core/encryption-and-signing-certificates.md)   
 [暗号化されたメッセージの送受信](../core/sending-and-receiving-encrypted-messages.md)