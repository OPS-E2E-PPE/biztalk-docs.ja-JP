---
title: BizTalk メッセージ コンテキストのプロパティに関する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc700e43-a44c-482b-b91c-9f1d997a486a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49d802ad2ca50538c25182311c68604c26d5a832
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225498"
---
# <a name="about-biztalk-message-context-properties"></a>BizTalk メッセージ コンテキストのプロパティについて
ドキュメントを受信すると、BizTalk Server アダプターは、そのドキュメントの BizTalk メッセージを作成します。 BizTalk メッセージには、受信したメッセージと共に、メッセージ コンテキストが含まれます。 メッセージ コンテキストは、BizTalk Server がドキュメントを処理する際に使用する、さまざまなプロパティのコンテナーです。 メッセージ コンテキストの各プロパティは、名前、名前空間、および値の 3 つで構成されています。 たとえば、次のメッセージ コンテキスト プロパティは、ドキュメントのインターチェンジ ID を示します。  
  
```  
<Property Name="InterchangeID" Namespace="http://schemas.microsoft.com/BizTalk/2003/system-properties" Value="{AC07BF30-2F1A-42B0-8390-191EF38BA839}"/>  
```  
  
 メッセージ コンテキスト プロパティは、メッセージが BizTalk Server を通過する際に、メッセージの有効期間全体にわたってメッセージ コンテキストに追加されます。  
  
 BizTalk で使用されるメッセージ コンテキスト プロパティには、以下に示す 2 種類があります。  
  
## <a name="property-fields"></a>プロパティ フィールド  
 プロパティ フィールドは、BizTalk メッセージング エンジンが、ドキュメントのルーティング、メッセージの追跡、およびオーケストレーションでの評価のために使用する、メッセージ コンテキスト プロパティです。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の BizTalk Server スキーマ エディターを使用してドキュメント スキーマを編集することにより、ドキュメントのフィールドを、プロパティ フィールドとしてメッセージ コンテキストに明示的に昇格させることができます。 ドキュメントのフィールドを、プロパティ フィールドとしてメッセージ コンテキストに書き込むには、ドキュメント スキーマにプロパティ スキーマが関連付けられている必要があります。 プロパティ フィールドは 255 文字までに制限されています。 **IsPromoted**メッセージ コンテキストのプロパティ フィールドのプロパティに設定されて**True**です。  
  
## <a name="distinguished-fields"></a>識別フィールド  
 識別フィールドは、個別のプロパティ スキーマを必要とせず、オーケストレーションからのアクセスのみ可能なメッセージ コンテキスト プロパティです。 識別フィールドは、ルーティングまたは追跡のために使用できません。 識別フィールドは個別のプロパティ スキーマを必要としないため、オーケストレーション エンジンによる識別フィールドの評価は、オーケストレーション エンジンによるプロパティ フィールドの評価より、オーバーヘッドが少なくて済みます。 プロパティ フィールドの評価には XPath クエリが必要ですが、識別フィールドの評価では、パイプラインの逆アセンブラーによりコンテキストの識別フィールドに値が設定され、オーケストレーション エンジンでキャッシュ値が読み取られるため、XPath クエリは必須ではありません。 ただし、オーケストレーション エンジンがコンテキストのプロパティを見つけられない場合、オーケストレーション エンジンは、値を見つけるために XPath クエリを開始します。 識別フィールドには、サイズの制限もありません。 **IsPromoted** 、メッセージ コンテキストの識別フィールドのプロパティに設定されて**False**です。  
  
## <a name="summary-of-differences-between-property-fields-and-distinguished-fields"></a>プロパティ フィールドと識別フィールドの違いの概要  
 次の表は、プロパティ フィールドと識別フィールドの相違点および類似点をまとめたものです。  
  
|**属性**|**プロパティ フィールド**|**識別フィールド**|  
|-------------------|------------------------|-----------------------------|  
|IsPromoted Property|True|False|  
|サイズの制限|255 文字|制限なし|  
|ルーティングのための使用|はい|不可|  
|追跡のための使用|はい|不可|  
|オーケストレーションでの使用|はい|はい|  
|プロパティ スキーマの必要性|はい|不可|  
|パイプラインおよびポートからのアクセス|はい|不可|  
  
## <a name="see-also"></a>参照  
 [メッセージ処理を制御するメッセージの内容を使用する方法](../core/ways-to-use-message-content-to-control-message-processing.md)