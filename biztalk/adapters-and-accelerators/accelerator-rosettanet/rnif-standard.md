---
title: "RNIF 規格 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RNIF, message definitions
- RNIF, messaging framework patterns
- messages, message definitions
- RNIF, standards
- messages, messaging framework patterns
ms.assetid: d39a9683-1ef5-462b-9472-4e30fe873f7d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6b29d8c9c770893fd78769b86266ce33e31a336
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="rnif-standard"></a>RNIF 規格
RNIF (RosettaNet Implementation Framework) 規格では、システムが RosettaNet メッセージを転送する方法が規定されています。 RNIF 規格は、堅牢な転送、ルーティング、パッケージ化、およびセキュリティの規格です。 RosettaNet 認定を受けるためには、すべての RosettaNet メッセージング システムが RNIF 規格に準拠している必要があります。  
  
 RNIF 規格では、メッセージ構造、受信確認の必要性、MIME (Multipurpose Internet Mail Extensions) エンコード、およびデジタル署名が規定されています。 RNIF のコア規格には、認証、承認、暗号化、および否認不可についての要件が含まれています。 RNIF 規格は、HTTP、MIME、および XML の各規格に基づいています。 RNIF 規格では、プラットフォームや使用アプリケーションは指定されていません。  
  
 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]2 つのバージョンの RNIF を実装します。 [RNIF Specification v02.00.01] と RNIF Specification v1.1 です。 RNIF 2.01 では、暗号化、添付ファイル、および同期トランザクションを含む、RNIF 1.1 でサポートされているもの以外の重要な機能を追加します。 RNIF 2.0 には RNIF 1.1 との下位互換性はありません。  
  
## <a name="messaging-framework-patterns"></a>メッセージング フレームワーク パターン  
 次の表に、メッセージング フレームワーク パターンおよび同期メッセージ交換に関する RNIF のサポートを示します。 シングル アクション メッセージとは、応答を含まないメッセージです。ダブル アクション メッセージとは、要求と応答が含まれるメッセージです。  
  
|Framework|パターン|同期/<br />非同期|  
|---------------|-------------|---------------------------------|  
|RNIF 1.1|Notification|非同期|  
|RNIF 1.1|トランザクション|非同期|  
|RNIF 2.0|ダブル アクション|同期|  
|RNIF 2.0|ダブル アクション|非同期|  
|RNIF 2.0|シングル アクション|同期|  
|RNIF 2.0|シングル アクション|非同期|  
  
## <a name="message-definitions"></a>メッセージの定義  
 RNIF 1.1 と RNIF 2.01 では、RosettaNet メッセージの定義が異なります。 添付ファイル、SMIME (Secure/Multipurpose Internet Mail Extensions) エンベロープ、Delivery Header、および MIME パッケージの処理方法などの定義が異なります。 特に、RNIF 2.01 では添付ファイルが含まれ、Delivery Header を追加しますが、RNIF 1.1 では Delivery Header を追加しません。  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]サポートしていません、 *Technical Recommendations for RNIF 1.1* (添付ファイルのサポート、および同期応答の 1 つ) は、RosettaNet 組織によって発行されました。  
  
 システムでは、パーティ識別、ルーティング、およびサービス レベルでの識別のために、RNIF 1.1 メッセージと RNIF 2.01 メッセージの一部を使用します。 メッセージの主要コンテンツとなる Service Content の本文を読み込み、返信する前に、各パーティがヘッダー値を設定または解釈できる必要があります。  
  
 次の図で、RNIF 1.1 と RNIF 2.01 のメッセージ定義について説明します。  
  
 ![(& m); 60変更なし &#62;。] (../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-rnif-message-definitions.gif "RN3_RNIF_Message_Definitions")  
  
 RNIF 1.1 メッセージでは、バージョン番号は RNIF バージョンを示します。 コンテンツ長は、RosettaNet サービス メッセージの長さです。 Preamble、Service Header、および Service Content を含むサービス メッセージは、1 つの Multipart/Related MIME エンティティとなります。 署名長は、バイト単位での署名の長さです。 署名が存在する場合、これはサービス メッセージ フィールド上の PKCS (Public-Key Cryptography Standards) # 7 署名です。  
  
 RNIF 2.01 には、ビジネス ペイロード、ヘッダー コンポーネント、およびシステムがパッケージ内で交換するその他の要素をまとめてパッケージ化する、プロトコルに依存しない転送コンテナーが含まれます。 RNIF 2.01 で定義されているように、RosettaNet Business Message には、Preamble、Delivery Header、Service Header、および Service Content が含まれます。 システムでは、RosettaNet 標準の文書型定義 (DTD) の文法検証ルールに基づいて、すべての要素を、その要素を含んでいる文書型のスキーマと突き合わせて検証する必要があります。 Service Content には、アクション メッセージとシグナル メッセージのどちらも使用できます。 Service Content がアクション メッセージである場合、メッセージに 1 つまたは複数の添付ファイルを含めることができます。  
  
 RosettaNet Business Message は、Multipart/Related MIME エンティティです。 前の図で示したように、MIME Multipart/Related 構造を使用して、ヘッダーと Service Content がパッケージ化されます。これは、RNIF 1.1 のパッケージング方法と似ています。 システムでは、必要に応じて RosettaNet Business Message に対してデジタル署名できます。 RNIF 1.1 の場合、そのために RNO (RosettaNet Object) 形式を使用します。 RNIF 2.0 では RNO 形式は使用されず、標準の S/MIME エンコードを使用します。  
  
 RNIF 2.01 ペイロードまたはペイロード コンテナーの暗号化が必要な場合があります。 それには、暗号化する部分を Multipart/Related MIME エンティティにバンドルし、暗号化します。 その後、生成された S/MIME オブジェクトを RosettaNet Business Message の一部としてパッケージ化します。  
  
 シグナル メッセージは、常に RosettaNet 定義のシグナル メッセージ インスタンスである必要があります。 アクション メッセージについては、RNIF 2.01 仕様で、サード パーティ定義の形式によるビジネス アクション メッセージを配布するオプションが用意されています。 RNIF 2.01 Service Header には、この目的のための追加フィールドが含まれています。標準の本文を識別するフィールドや、アクション メッセージが準拠する仕様のバージョンを識別するフィールドなどです。  
  
 アクション メッセージ (ビジネス コンテンツとも呼ばれます) のみ、発信元が非 RosettaNet であってもかまいません。 システムでは、RosettaNet 定義の PIP でこれらのメッセージを交換する必要があります。 RosettaNet は、PIP 仕様の認可サード パーティのアクション メッセージを明示的に識別することにより、これらのメッセージを許可する必要があります。 さらに、取引先は、サード パーティのビジネス コンテンツを交換するための取引先アグリーメントに同意している必要があります。 このアグリーメントには、PIP ペイロードのバインド情報が含まれている必要があります。この情報によって、PIP の特定のアクション メッセージに置き換えて使用するサード パーティのビジネス コンテンツを識別します。  
  
## <a name="see-also"></a>参照  
 [RosettaNet および CIDX メッセージ規格](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)