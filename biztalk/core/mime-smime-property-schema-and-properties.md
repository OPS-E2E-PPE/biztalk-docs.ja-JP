---
title: MIME-SMIME プロパティ スキーマおよびプロパティ |Microsoft Docs
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
ms.openlocfilehash: b7631422189de4ab2e92d3a54d34032e949e8e84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394453"
---
# <a name="mime-smime-property-schema-and-properties"></a>MIME-SMIME プロパティ スキーマおよびプロパティ

## <a name="namespace-properties"></a>Namespace プロパティ
**http://schemas.microsoft.com/BizTalk/2003/mime-properties**名前空間には、MIME/SMIME エンコーダー パイプライン コンポーネントのメッセージおよび部分コンテキスト プロパティを設定するために使用できるプロパティが含まれています。 MIME/SMIME エンコーダーでは、これらのプロパティを使用して、作成されるメッセージで、適切な MIME/SMIME ヘッダーを生成します。 次の表では、MIME/SMIME プロパティについて説明します。  
  
|プロパティ|スコープ|型|説明|  
|--------------|-----------|----------|-----------------|  
|**FileName**|メッセージ部分ごと|xs:string|MIME/SMIME 部分のファイル名ヘッダーを設定します。|  
|**ContentID**|メッセージ部分ごと|xs:string|MIME/SMIME 部分の CONTENT-ID ヘッダーを設定します。|  
|**ContentDescription**|メッセージ部分ごと|xs:string|MIME/SMIME 部分の Content-description ヘッダーを設定します。|  
|**ContentTransferEncoding**|メッセージ部分ごと|xs:string|生成した MIME/SMIME 部分のコンテンツ-転送-エンコード ヘッダーを設定します。<br /><br /> この値はオーバーライド、**コンテンツ転送エンコード**パイプライン デザイナーで構成されている値。 マルチパート メッセージの場合は、さまざまな MIME/SMIME 部分の異なるエンコードを使用できます。|  
|**ContentLocation**|メッセージ部分ごと|xs:string|生成した MIME/SMIME 部分のコンテンツ-場所ヘッダーを設定します。|  
|**IsMIMEEncoded**|メッセージ部分ごと|xs:boolean|メッセージが MIME/SMIME ペイロードを持つかどうかを指定します。 MIME コンポーネントは、これを設定する必要はありませんので、この値を書き込みます。|  
  
 MIME/SMIME エンコーダーから次のパーツのプロパティも使用して、**システム**名前空間。  
  
|プロパティ|型|説明|  
|--------------|----------|-----------------|  
|ContentType|xs:string|生成した MIME/SMIME 部分の Content-type ヘッダーに対応します。|  
|FileName|xs:string|ファイル名に対応します。|  
  
## <a name="see-also"></a>参照  
 [MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)   
 [MIME-SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [MIME (BizTalk Server サンプル)](../core/mime-biztalk-server-sample.md)   
 **メッセージ コンテキスト プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]