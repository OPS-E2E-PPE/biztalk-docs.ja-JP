---
title: BTARN 送信パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler
- send pipelines, message flow
- DOCTYPE headers
- MIME/SMIME Encoder
- send pipelines, BTARN
- BTARN, send pipelines
- XML Preprocessor
- messages, message flow
ms.assetid: 88562132-0ea4-4b5a-9445-b69f6c84e5ea
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62c86e810ad185f7497f73c1b4d4d53cffe8f29e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284872"
---
# <a name="btarn-send-pipeline"></a>BTARN 送信パイプライン
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend パイプライン (RNIFSend.btp) で転送するために RosettaNet Implementation Framework (RNIF) メッセージを準備します。 送信パイプラインは、次のとおりです。  
  
-   XML プリプロセッサ  
  
-   XML アセンブラー  
  
-   Multipurpose Internet Mail Extensions Multipurpose Internet Mail Extensions (MIME/SMIME) エンコーダー  
  
## <a name="xml-preprocessor"></a>XML プリプロセッサ  
 XML プリプロセッサは、メッセージに DOCTYPE ヘッダーを追加します。 ヘッダーは、メッセージに関連付けられているドキュメント型定義 (DTD) スキーマを識別します。 RNIF 仕様では、RNIF 送信の DOCTYPE ヘッダーの存在が必要です。  
  
## <a name="xml-assembler"></a>XML アセンブラー  
 XML アセンブラーは、BizTalk Server の XML アセンブラに基づいています。 プロパティをメッセージ コンテキストからエンベロープおよびドキュメントに転送します。 XML 部分および添付ファイルからメッセージをアセンブルします。 メッセージの検証は実行されません。  
  
 詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML アセンブラー、BizTalk Server ヘルプの「XML アセンブラー パイプライン コンポーネント」を参照してください。  
  
## <a name="mimesmime-encoder"></a>MIME/SMIME エンコーダー  
 MIME/SMIME エンコーダーは、BizTalk Server の MIME/SMIME エンコーダに基づいています。 取引先のパートナー契約と、BizTalk Server の MIME/SMIME エンコーダーの設定のプロトコル設定に応じて、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]エンコーダーは、次を実行します。  
  
- RNIF 1.1 メッセージを必要に応じて、メッセージには、8 バイトのバイナリ ヘッダーを追加します。  
  
- メッセージの部分をエンコードし、ダイジェストを計算します。  
  
- (Service content と添付ファイル) のペイロードまたはペイロード コンテナー (service content とヘッダーのサービスとの添付ファイル) を暗号化します。 設定した場合、**すべてのポートをエンコード**の設定、**プロトコル**を取引先アグリーメントのタブ`False`、エンコーダはペイロードのみを暗号化します。 設定した場合、**すべてのポートをエンコード**設定`True`、エンコーダはペイロード コンテナーを暗号化します。  
  
  詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MIME/SMIME エンコーダーでは、BizTalk Server ヘルプの「MIME/SMIME エンコーダー パイプライン コンポーネント」を参照してください。  
  
## <a name="message-flow"></a>メッセージ フロー  
 メッセージ フローは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]送信パイプラインは、次のようにします。  
  
1.  設定した場合、**すべての部分のエンコード**を取引先アグリーメントの設定`True`、MIME/SMIME エンコーダはすべてのメッセージ部分をエンコードします。 エンコード方式で設定が使用されます、`Encoding`アグリーメントのプロパティ。  
  
2.  RNIF 2.01 では、メッセージがアクション メッセージと添付ファイルがある場合、エンコーダーは次の処理添付ファイルごとに。  
  
    1.  添付ファイルがバイナリの場合は、エンコーダーによってエンコードされます。  
  
    2.  エンコーダーは、添付ファイルのコンテンツ ID が生成されます。  
  
    3.  エンコーダーでは、添付ファイルの MIME パートを作成します。  
  
3.  RNIF 2.01 では、パイプラインはメッセージ部分を暗号化しの設定に応じて RNIF メッセージを作成する**永続的な機密性**(として、プロセス構成設定で設定)。  
  
    1.  設定した場合**永続的な機密性**に**ペイロード**エンコーダーは service content と添付ファイルを暗号化します。 アセンブラーは、service header、delivery header、および preamble を RNIF メッセージを完成し追加します。  
  
    2.  設定した場合**永続的な機密性**に**ペイロード コンテナー**エンコーダーは service header、service content と添付ファイルを暗号化します。 アセンブラーは delivery header と preamble 最後の RNIF メッセージを追加します。  
  
    3.  設定した場合**永続的な機密性**に**None**アセンブラーは service content と添付ファイルを含めずに、service header、delivery header、および preamble が追加されます暗号化) をクリックし、最後の RNIF メッセージを構築します。  
  
4.  RNIF 1.1 では、アセンブラーは暗号化なしの最後の RNIF メッセージを構築します。  
  
5.  エンコーダーは、次の例でメッセージに署名されます。  
  
    1.  メッセージがシグナル メッセージでは、および**否認不可のために必要な**プロパティ (プロセス構成の設定) では、`True`します。  
  
    2.  メッセージがアクション メッセージでは、および**発信元とコンテンツの否認**プロパティ (プロセス構成の設定) では、`True`します。  
  
6.  RNIF 2.01 では、エンコーダーは、MIME メッセージの最初のボディ部のダイジェストを計算し、ダイジェストを保持します。 メソッドのセットを使用してダイジェストを計算には、`Digest`取引先アグリーメント (sha-1 または MD5) のメソッドのプロパティ。  
  
## <a name="see-also"></a>参照  
 [BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)