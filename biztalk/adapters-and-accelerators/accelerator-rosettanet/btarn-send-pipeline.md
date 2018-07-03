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
ms.openlocfilehash: 0791ab4714e1e8a9de847a60d17d14e38f095ecf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011635"
---
# <a name="btarn-send-pipeline"></a>BTARN 送信パイプライン
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend パイプライン (RNIFSend.btp) で転送するために RosettaNet Implementation Framework (RNIF) メッセージを準備します。 送信パイプラインには、次のものが組み込まれています。  
  
-   XML プリプロセッサ  
  
-   XML アセンブラー  
  
-   MIME/SMIME (Multipurpose Internet Mail Extensions/SecureMultipurpose Internet Mail Extensions) エンコーダー  
  
## <a name="xml-preprocessor"></a>XML プリプロセッサ  
 XML プリプロセッサは、メッセージに DOCTYPE ヘッダーを追加します。 このヘッダーは、メッセージに関連付けるドキュメント型定義 (DTD) スキーマを指定します。 RNIF 仕様には、RNIF 送信のための DOCTYPE ヘッダーが必要です。  
  
## <a name="xml-assembler"></a>XML アセンブラー  
 XML アセンブラーは、BizTalk Server の XML アセンブラに基づいています。 XML アセンブラーは、メッセージ コンテキストからエンベロープとドキュメントにプロパティを転送します。 そして、XML 部分および添付ファイルからメッセージを構築します。 メッセージの検証は実行しません。  
  
 詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML アセンブラー、BizTalk Server ヘルプの「XML アセンブラー パイプライン コンポーネント」を参照してください。  
  
## <a name="mimesmime-encoder"></a>MIME/SMIME エンコーダ  
 MIME/SMIME エンコーダーは、BizTalk Server の MIME/SMIME エンコーダに基づいています。 取引先のパートナー契約と、BizTalk Server の MIME/SMIME エンコーダーの設定のプロトコル設定に応じて、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]エンコーダーは、次を実行します。  
  
- RNIF 1.1 メッセージに必要な 8 バイトのバイナリ ヘッダーをメッセージに追加します。  
  
- メッセージ部分をエンコードし、ダイジェストを計算します。  
  
- ペイロード (Service Content と添付ファイル) またはペイロード コンテナー (Service Content、Service Header、および添付ファイル) を暗号化します。 設定した場合、**すべてのポートをエンコード**の設定、**プロトコル**を取引先アグリーメントのタブ`False`、エンコーダはペイロードのみを暗号化します。 設定した場合、**すべてのポートをエンコード**設定`True`、エンコーダはペイロード コンテナーを暗号化します。  
  
  詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]MIME/SMIME エンコーダーでは、BizTalk Server ヘルプの「MIME/SMIME エンコーダー パイプライン コンポーネント」を参照してください。  
  
## <a name="message-flow"></a>メッセージ フロー  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 送信パイプラインを経由するメッセージ フローは次のとおりです。  
  
1.  設定した場合、**すべての部分のエンコード**を取引先アグリーメントの設定`True`、MIME/SMIME エンコーダはすべてのメッセージ部分をエンコードします。 アグリーメントの `Encoding` プロパティに設定されているエンコード方式が使用されます。  
  
2.  RNIF 2.01 では、メッセージがアクション メッセージで添付ファイルがある場合、エンコーダーは各添付ファイルに対して次の処理を実行します。  
  
    1.  添付ファイルがバイナリの場合は、エンコーダーがエンコードします。  
  
    2.  エンコーダーは、添付ファイルのコンテンツ ID を生成します。  
  
    3.  エンコーダーは、添付ファイルの MIME 部分を作成します。  
  
3.  RNIF 2.01 では、パイプラインはメッセージ部分を暗号化しの設定に応じて RNIF メッセージを作成する**永続的な機密性**(として、プロセス構成設定で設定)。  
  
    1.  設定した場合**永続的な機密性**に**ペイロード**エンコーダーは service content と添付ファイルを暗号化します。 次に、アセンブラーは Service Header、Delivery Header、および Preamble を追加して RNIF メッセージを完成します。  
  
    2.  設定した場合**永続的な機密性**に**ペイロード コンテナー**エンコーダーは service header、service content と添付ファイルを暗号化します。 次に、アセンブラーは Delivery Header と Preamble を追加して RNIF メッセージを完成します。  
  
    3.  設定した場合**永続的な機密性**に**None**アセンブラーは service content と添付ファイルを含めずに、service header、delivery header、および preamble が追加されます暗号化) をクリックし、最後の RNIF メッセージを構築します。  
  
4.  RNIF 1.1 では、アセンブラーは暗号化せずに RNIF メッセージを完成します。  
  
5.  次の場合、エンコーダーはメッセージに署名します。  
  
    1.  メッセージがシグナル メッセージでは、および**否認不可のために必要な**プロパティ (プロセス構成の設定) では、`True`します。  
  
    2.  メッセージがアクション メッセージでは、および**発信元とコンテンツの否認**プロパティ (プロセス構成の設定) では、`True`します。  
  
6.  RNIF 2.01 では、エンコーダーは MIME メッセージの最初の本文部分のダイジェストを計算して、保持します。 エンコーダーは取引先アグリーメント (SHA-1 または MD5) の `Digest` メソッド プロパティのメソッド セットを使用してダイジェストを計算します。  
  
## <a name="see-also"></a>参照  
 [BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)