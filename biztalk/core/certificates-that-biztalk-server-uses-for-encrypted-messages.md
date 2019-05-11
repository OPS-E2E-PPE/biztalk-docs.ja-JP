---
title: 暗号化されたメッセージを BizTalk Server で使用する証明書 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message flow [encrypted messages]
- encrypted messages
- messages, encryption
ms.assetid: 44b06488-4ecd-436d-af3d-b95e285ecb3e
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b96e47a84e94067cf197fd8614ef789af0a012ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358008"
---
# <a name="certificates-that-biztalk-server-uses-for-encrypted-messages"></a>BizTalk Server は、暗号化されたメッセージで使用する証明書
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信メッセージの公開キーの暗号化と Secure Multipurpose Internet Mail Extensions (S/MIME) に基づいて、受信メッセージの解読をサポートしています。 BizTalk Server では、S/MIME バージョン 3 の送信メッセージの暗号化と S/MIME バージョン 2 および 3 の受信メッセージを復号化を使用します。  
  
- BizTalk Server では、RSA および Diffie Hellman 暗号化証明書をサポートします。  
  
- BizTalk Server には、データ暗号化標準 (DES)、3 des、および RC2 暗号化アルゴリズムがサポートしています。  
  
  次の図は、BizTalk Server は暗号化されたメッセージを受信すると、メッセージ フローを示します。  
  
  ![暗号化されたメッセージを受信するときに、メッセージ フロー](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")  
  
  BizTalk Server は暗号化されたメッセージを受信するときのメッセージ フローは次のとおりです。  
  
1. パートナーから BizTalk Server にメッセージが送信されます。 パートナーは、BizTalk Server の公開キーで、メッセージを暗号化します。  
  
2. 対応する BizTalk Server 受信ハンドラーでメッセージが受信されます。  
  
3. 受信パイプラインの実行中には、MIME/SMIME デコーダー パイプライン コンポーネントは、BizTalk Server 秘密キーを使用してメッセージを解読します。  
  
   > [!NOTE]
   >  IIS 7.0 コンピューターで成功するパイプラインの復号化は、IIS アプリケーション プール アカウントと受信ハンドラーに関連付けられているホスト インスタンスによって使用されるアカウントは、同じであると、このアカウントがのメンバーであることを確認、 \<machineName\>\IIS_WPG グループ。 IIS の設定の詳細については、プロセス id の IIS 7.0 を参照してください[IIS アクセス許可の問題を解決するためのガイドライン](../core/guidelines-for-resolving-iis-permissions-problems.md)します。 これらのプロセスは同じアカウントで実行する必要があります。これは、アカウント プロファイルが読み込まれ、それに続いてパイプラインで解読を実行するのに必要なレジストリ キーが読み込まれるようにするためです。 パフォーマンス上の理由は、BizTalk がアカウント プロファイルとレジストリ キーを読み込むように、同じアカウントで、BizTalk ホスト インスタンスを構成する必要がありますので、関連する w3wp.exe プロセスを開始するときに、IIS 7.0 は、アカウントのプロファイルを読み込みません。  
  
4. 追加処理が実行されます。  
  
   次の図は、BizTalk Server は、暗号化されたメッセージを送信するときに、メッセージ フローを示します。  
  
   ![暗号化されたメッセージを送信するときに、メッセージ フロー](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")  
  
   BizTalk Server は、パートナーに暗号化されたメッセージを送信するときのメッセージ フローは次のとおりです。  
  
5. 対応する BizTalk Server 送信ハンドラーからパートナーにメッセージが送信されます。  
  
6. 送信パイプラインの実行中には、MIME/SMIME エンコーダー パイプライン コンポーネントは、パートナーの公開キーを使用して、メッセージを暗号化します。  
  
7. パートナーが BizTalk Server からメッセージを受信します。 パートナーは、メッセージの解読にその秘密キーを使用します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server は、署名付きメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [BizTalk Server で使用される証明書ストア](../core/certificate-stores-that-biztalk-server-uses.md)   
 [暗号化および署名証明書](../core/encryption-and-signing-certificates.md)   
 [暗号化されたメッセージの送受信](../core/sending-and-receiving-encrypted-messages.md)