---
title: "スキーマの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing, schemas
- schemas, developing
ms.assetid: 123c4b43-34e4-41c7-980d-5d518b1479c1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1c12936f2883bfdbcdcd80d300d2ab5a9ff58d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-schemas"></a>スキーマの操作
指定されたスキーマ[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]は、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Worldwide 銀行間財務通信 (SWIFT) FIN メッセージの社会の XSD 表記します。 各メッセージの種類は、SWIFT ヘッダーとトレーラーの SWIFT (インターチェンジの形式) を含む独自のスキーマがします。 このスキーマは、SWIFT メッセージの送受信に十分です。 これらのスキーマは、フラット ファイル FIN 構造体の詳細な XML 表現を提供する、区切り文字および位置指定レコードの一意の組み合わせ。  
  
 SWIFT のほとんどのお客様は、SWIFT FIN メッセージの比較的小さなサブセットを使用します。 これらの顧客のソリューションを実装するには、BizTalk スキーマ プロジェクトを作成することができます (で示したように[第 2 章: 新しいスキーマ プロジェクトに追加する](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)A4SWIFT チュートリアルの)。 関連するメッセージのスキーマを追加 (MT*xxx*.xsd) から\\\ files \microsoft BizTalk Accelerator for SWIFT\<バージョン > MessagePack\SWIFT Messages\A4SWIFT SRG\<バージョン > \X は xyy と FIN メッセージ型の最初の桁カテゴリ x\MT xyy ディレクトリは、メッセージの 3 桁のメッセージの種類です。  
  
 いくつかのスキーマは、同じプロジェクトに追加できます。 管理の容易性を維持するためには、プロジェクトごとに 20 件以上のメッセージ スキーマを追加しないでください。 また、基本クラスと共通のスキーマをプロジェクトに追加する必要があります。 基本クラスと共通のスキーマが既にある場合は、それらを展開するのではなく、そのアセンブリへの参照を作成する必要があります。 このセクションでは、これらのスキーマについて説明します。 メッセージ スキーマは、SWIFT ネットワークに送信されたメッセージと SWIFT から受信したメッセージの両方が使用する準備ができています。  
  
 内の各 SWIFT スキーマの内容を調べることができます[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]スキーマ エディターを使用します。 次の一般的な構造であるすべてのメッセージ交換スキーマ。  
  
-   ヘッダー  
  
-   [メッセージ テキスト]  
  
-   トレーラー  
  
 このセクションでは、ヘッダーとトレーラーのスキーマについて説明します。 メッセージ テキストは、FIN メッセージのペイロードを構成および、送信者、受信者、およびメッセージの種類を含むフィールドを除くデータ フィールドのすべてが含まれます。 これら 3 つのフィールドは、ヘッダー部分に含まれます。 一部のメッセージには、処理情報も提供する、省略可能なユーザー ヘッダーも含まれます。  
  
 各 FIN メッセージ ペイロードは、一連のフィールドに定義されたシーケンス内で構成されます。 これらのフィールドは、次の規則に従います。  
  
-   フィールドには、必須または、シーケンス内でオプションがあります。  
  
-   シーケンスがサブ シーケンス、およびサブ シーケンスがシーケンス内で繰り返す必要があります。  
  
-   いくつかのメッセージ型のフィールドを使用することができます。  
  
-   フィールドの内部に、要素またはサブフィールドが可能性があります。 要素またはサブフィールドをいくつかのフィールドに一般的な可能性があります。  
  
-   グループ ノードでは、各繰り返しのシーケンスを表します。  
  
-   各フィールド自体があります、複数の節レベル レコードとして各説明します。  
  
-   スキーマ要素は、最下位レベルのサブフィールドのみを表します。  
  
-   共通の基本とスキーマは、共通のレコードと要素を定義します。  
  
-   スキーマは、いくつかの形式 (パーティ フィールドなど) の一部のフィールドを表します。 スキーマは、選択フィールドとして、このようなフィールドを定義します。  
  
-   一部のフィールドには、値のセットが制限されます。 ほとんどの場合、スキーマには、これらの値が一覧表示します。 スキーマ定義には、文字セットの検証も含まれます。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [ベースと一般的なスキーマ](../../adapters-and-accelerators/accelerator-swift/base-and-common-schemas.md)  
  
-   [SWIFT ヘッダーおよびトレーラ スキーマ](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  
  
-   [SWIFT スキーマの名前付け規則](../../adapters-and-accelerators/accelerator-swift/swift-schema-naming-conventions.md)