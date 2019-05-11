---
title: BizTalk メッセージ コンテキストのプロパティについて |Microsoft Docs
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
ms.openlocfilehash: 6eb7277ab741dc1a33dd7d905048db3d411c02d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362381"
---
# <a name="about-biztalk-message-context-properties"></a>BizTalk メッセージ コンテキストのプロパティについて
ドキュメントが BizTalk Server アダプターによって受信されると、アダプターは、ドキュメントの BizTalk メッセージを作成します。 BizTalk メッセージには、メッセージ コンテキストと受信したドキュメントが含まれています。 メッセージ コンテキストは、ドキュメントを処理するときに BizTalk Server で使用されるさまざまなプロパティのコンテナーです。 メッセージ コンテキスト内の各プロパティは、次の 3 つ、名前、名前空間、および値で構成されます。 たとえば、次のメッセージ コンテキスト プロパティには、ドキュメントのインターチェンジ ID がについて説明します。  
  
```  
<Property Name="InterchangeID" Namespace="http://schemas.microsoft.com/BizTalk/2003/system-properties" Value="{AC07BF30-2F1A-42B0-8390-191EF38BA839}"/>  
```  
  
 メッセージ コンテキスト プロパティは、BizTalk Server を通過すると、メッセージの有効期間にわたってメッセージ コンテキストに追加されます。  
  
 以下に示すように BizTalk で使用されるメッセージ コンテキスト プロパティの 2 つの異なる種類あります。  
  
## <a name="property-fields"></a>プロパティ フィールド  
 プロパティ フィールドは、BizTalk メッセージング エンジンによってオーケストレーションでの評価、ドキュメントのルーティング、メッセージの追跡の目的で使用されるメッセージ コンテキスト プロパティ。 明示的に昇格させるドキュメント内のフィールドをメッセージ コンテキスト プロパティ フィールドとしてで、BizTalk Server スキーマ エディターで使用できるドキュメントのスキーマを編集して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 ドキュメントのフィールドをプロパティ フィールドとしてメッセージ コンテキストに書き込む、ドキュメント スキーマは、関連付けられているプロパティ スキーマをいる必要があります。 プロパティ フィールドは、255 文字に制限されます。 **IsPromoted**メッセージ コンテキストのプロパティ フィールドのプロパティに設定されて**True**します。  
  
## <a name="distinguished-fields"></a>識別フィールド  
 識別フィールドは、メッセージ コンテキスト プロパティを個別のプロパティ スキーマを必要としないと、オーケストレーションからアクセスできるのみです。 識別フィールドは、ルーティングまたは追跡のため使用できません。 識別フィールドは、個別のプロパティ スキーマを必要としないため、オーケストレーション エンジンによる識別フィールドの評価は、オーケストレーション エンジンによってプロパティ フィールドの評価よりもオーバーヘッドが少ないを使用します。 識別フィールドの評価は必要ありません、XPath クエリ パイプラインの逆アセンブラーがコンテキストの識別フィールドを設定し、オーケストレーション エンジンが、キャッシュされた値を読み取り、プロパティ フィールドの評価に XPath クエリが必要です。 ただし、オーケストレーション エンジンは、コンテキストのプロパティを見つけられない場合、値を検索する XPath クエリから開始されます。 識別フィールドには、サイズの制限はありません。 **IsPromoted**メッセージ コンテキストの識別フィールドのプロパティに設定されて**False**します。  
  
## <a name="summary-of-differences-between-property-fields-and-distinguished-fields"></a>プロパティ フィールドと識別フィールドの違いの概要  
 次の表は、プロパティ フィールドと識別フィールドの類似点と相違点をまとめたものです。  
  
|**属性**|**プロパティ フィールド**|**識別フィールド**|  
|-------------------|------------------------|-----------------------------|  
|IsPromoted プロパティ|True|False|  
|サイズの制限|255 文字|制限なし|  
|ルーティングに使用|はい|いいえ|  
|追跡の使用|はい|いいえ|  
|オーケストレーションで使用されます。|はい|はい|  
|プロパティ スキーマが必要です。|はい|いいえ|  
|パイプラインおよびポートからアクセスできます。|はい|いいえ|  
  
## <a name="see-also"></a>参照  
 [メッセージ処理を管理するためのメッセージの内容の使用方法](../core/ways-to-use-message-content-to-control-message-processing.md)