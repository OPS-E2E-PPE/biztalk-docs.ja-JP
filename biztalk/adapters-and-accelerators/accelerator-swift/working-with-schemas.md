---
title: スキーマの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, schemas
- schemas, developing
ms.assetid: 123c4b43-34e4-41c7-980d-5d518b1479c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 411782fcc0f8d3c80382d1de3b7c8f31d49e1fc9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529650"
---
# <a name="working-with-schemas"></a>スキーマの使用
Microsoft で提供されるスキーマ[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]は世界銀行間金融電気通信 (SWIFT) FIN メッセージの社会の Microsoft XSD 表現です。 各種のメッセージでは、SWIFT ヘッダーと SWIFT トレーラー (インターチェンジの形式) を含む独自のスキーマがあります。 このスキーマは、SWIFT メッセージの送受信には十分です。 これらのスキーマは、フラット ファイル FIN 構造体の詳細な XML 表現を提供する、区切り文字および位置指定レコードの一意の組み合わせ。  

 SWIFT のほとんどのお客様は、SWIFT FIN メッセージの比較的小さなサブセットを使用します。 これらのお客様には、ソリューションを実装するには、BizTalk スキーマ プロジェクトを作成することができます (で示した[モジュール 2。新しいスキーマ プロジェクトの追加](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)A4SWIFT チュートリアルの)。 関連するメッセージのスキーマを追加 (MT*xxx*.xsd) から\\\ Program files \microsoft BizTalk Accelerator for SWIFT\<バージョン\>MessagePack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Category x\MT xyy ディレクトリ、x は FIN メッセージの種類の最初の桁、xyy は、メッセージの 3 桁のメッセージの種類。  

 いくつかのスキーマは、同じプロジェクトに追加できます。 管理の容易性を維持するには、プロジェクトごとに 20 件以上のメッセージ スキーマを追加しないでください。 また、基本と共通のスキーマをプロジェクトに追加する必要があります。 共通の基本クラスとスキーマを既にデプロイした場合は、それらを展開するのではなく、これらのアセンブリを参照する必要があります。 このセクションでは、これらのスキーマについて説明します。 メッセージ スキーマが SWIFT ネットワークに送信されるメッセージと SWIFT から受信したメッセージの両方として使用できます。  

 Microsoft では各 SWIFT スキーマの内容を調べることができます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]スキーマ エディターを使用します。 次の一般的な構造を持つすべてのメッセージのインターチェンジのスキーマと。  

- ヘッダー  

- [メッセージ テキスト]  

- トレーラー  

  このセクションでは、ヘッダーおよびトレーラのスキーマについて説明します。 メッセージ テキストは、FIN メッセージのペイロードで構成され、すべての送信者、受信者、およびメッセージの種類を含むフィールドを除くデータ フィールドが含まれています。 ヘッダー部分は、これら 3 つのフィールドに格納されます。 一部のメッセージには、処理情報を入力することも省略可能なユーザー ヘッダーも含まれます。  

  各 FIN メッセージのペイロードは、一連の定義された一連のフィールドで構成されます。 これらのフィールドは、次の規則に従います。  

- 必須またはオプション、シーケンス内のフィールドがあります。  

- シーケンスは、サブ シーケンスを含めることができ、サブ シーケンスがシーケンス内で繰り返すことがあります。  

- いくつかのメッセージの種類のフィールドを使用することができます。  

- フィールドの内部、要素またはサブフィールドに可能性があります。 要素またはサブフィールドをいくつかのフィールドに共通可能性があります。  

- グループ ノードでは、各繰り返しのシーケンスを表します。  

- 各フィールド自体があります、複数の節レベル レコードとして各説明。  

- スキーマの要素は、最下位レベルのサブフィールドのみを表します。  

- 一般的なと基本スキーマは、共通のレコードと要素を定義します。  

- スキーマは、いくつかの形式 (パーティのフィールド) などの一部のフィールドを表します。 スキーマは、選択フィールドとして、このようなフィールドを定義します。  

- 一部のフィールドには、値のセットが制限されます。 ほとんどの場合、スキーマには、これらの値が一覧表示します。 スキーマの定義には、文字セットの検証も含まれます。  

  このセクションには、次のトピックが含まれています。  

- [基本的なスキーマと一般的なスキーマ](../../adapters-and-accelerators/accelerator-swift/base-and-common-schemas.md)  

- [SWIFT ヘッダーおよびトレーラー スキーマ](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  

- [SWIFT スキーマの名前付け規則](../../adapters-and-accelerators/accelerator-swift/swift-schema-naming-conventions.md)
