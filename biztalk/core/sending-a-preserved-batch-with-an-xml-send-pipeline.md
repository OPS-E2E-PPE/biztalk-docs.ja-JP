---
title: "XML に保存されたバッチを送信する送信パイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6765576a-134f-4856-911c-2f603b6479bd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14bd61538398bb11967cbbe750a4fadc016a5168
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sending-a-preserved-batch-with-an-xml-send-pipeline"></a>XML 送信パイプラインによる保存されたバッチの送信
通常、保存されたバッチは、EDI 送信パイプラインを使用して送信します。 ただし、XML 送信パイプラインを使用して、保存されたバッチを送信することもできます。 EDI 受信パイプラインによって生成され、メッセージ ボックスにドロップされる場合の保存されたバッチは XML 形式であるため、XML 送信パイプラインでは、このバッチを XML 形式で渡します。  
  
 XML 送信パイプラインを使用して、保存されたバッチを送信するには、該当するバッチ スキーマと、インターチェンジの各メッセージの種類のドキュメント スキーマを持つプロジェクトを配置する必要があります。 また、プロジェクトで展開するバッチ スキーマの名前空間を変更することも必要です。 これを行わないと、保存されたバッチの XML ファイルがバッチ スキーマの名前空間と対応しなくなります。 バッチ スキーマの名前空間は、次の表に示すように変更する必要があります。  
  
|このエンコードの種類。|バッチ スキーマの変更前の名前空間|変更後の名前空間|  
|-----------------------------|------------------------------------------------|---------------------------------|  
|EDIFACT|`http://schemas.microsoft.com/Edi/Edifact`|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006/InterchangeXML`|  
|X12|`http://schemas.microsoft.com/Edi/X12_BatchSchema`|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006/InterchangeXML`|  
  
 これは、EDI アセンブラーの問題ではありません。  
  
## <a name="see-also"></a>参照  
 [EDI バッチの構成](../core/configuring-edi-batches.md)