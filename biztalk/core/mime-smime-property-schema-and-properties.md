---
title: MIME/SMIME プロパティ スキーマおよびプロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 26dd25b9-7eb8-4354-9929-dc1985dd1d77
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 882b25733a46b8b7b973c992d465132df4c47b75
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "22263194"
---
# <a name="mime-smime-property-schema-and-properties"></a>MIME/SMIME プロパティ スキーマおよびプロパティ

## <a name="namespace-properties"></a>Namespace プロパティ
**http://schemas.microsoft.com/BizTalk/2003/mime-properties**名前空間には、MIME/SMIME エンコーダー パイプライン コンポーネントのメッセージおよび部分コンテキストのプロパティを設定するために使用できるプロパティが含まれています。 MIME/SMIME エンコーダーは、これらのプロパティを使用して、作成されるメッセージの適切な MIME/SMIME ヘッダーを生成します。 次の表は、MIME/SMIME プロパティを示しています。  
  
|プロパティ|スコープ|型|Description|  
|--------------|-----------|----------|-----------------|  
|**ファイル名**|メッセージ部分ごと|xs:string|MIME/SMIME 部分のファイル名ヘッダーを設定します。|  
|**コンテンツ Id**|メッセージ部分ごと|xs:string|MIME/SMIME 部分のコンテンツ - ID ヘッダーを設定します。|  
|**ContentDescription**|メッセージ部分ごと|xs:string|MIME/SMIME 部分の Content-description ヘッダーを設定します。|  
|**ContentTransferEncoding**|メッセージ部分ごと|xs:string|生成した MIME/SMIME 部分のコンテンツ - 転送 - エンコード ヘッダーを設定します。<br /><br /> この値より優先、 **コンテンツ転送エンコード** パイプライン デザイナーで構成されている値。 マルチパート メッセージでは、さまざまな MIME/SMIME 部分に対して異なるエンコードを使用できます。|  
|**ContentLocation**|メッセージ部分ごと|xs:string|生成した MIME/SMIME 部分のコンテンツ - 場所ヘッダーを設定します。|  
|**IsMIMEEncoded**|メッセージ部分ごと|xs:boolean|メッセージが MIME/SMIME ペイロードを保有するかどうかを指定します。 MIME コンポーネントがこの値を書き込みます。このため、設定する必要はありません。|  
  
 MIME/SMIME エンコーダーもから次のパーツのプロパティを使用して、 **システム** 名前空間。  
  
|プロパティ|型|Description|  
|--------------|----------|-----------------|  
|ContentType|xs:string|生成した MIME/SMIME 部分のコンテンツ - 種類ヘッダーに対応します。|  
|FileName|xs:string|ファイル名に対応します。|  
  
## <a name="see-also"></a>参照  
 [MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)   
 [MIME/SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [MIME (BizTalk Server サンプル)](../core/mime-biztalk-server-sample.md)   
 **メッセージ コンテキスト プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]