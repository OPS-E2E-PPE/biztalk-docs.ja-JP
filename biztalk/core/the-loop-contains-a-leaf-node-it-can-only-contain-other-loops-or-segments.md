---
title: "ループにリーフ ノードが含まれています。 その他のループまたはセグメントを含めることができますのみ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a0ee5e6-519d-4c95-8681-de5a37741d56
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d03349389fb108d434cce67afc5be13fd2a3d513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-loop-contains-a-leaf-node-it-can-only-contain-other-loops-or-segments"></a>ループにリーフ ノードが含まれています。 ループに含めることができるのは、他のループまたはセグメントのみです
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|SchemaCode125ELoopContainsLeafNode|  
|メッセージ テキスト|ループにリーフ ノードが含まれています。 ループに含めることができるのは、他のループまたはセグメントのみです|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジがドキュメントのスキーマに準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。 この場合、ループには子のないリーフ ノードが含まれていましたが、スキーマではループには他のループまたはセグメントのみを含むことができると指定されています。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ループにリーフ ノードが含まれないようにインターチェンジの送信者にループを修正してもらい、インターチェンジを再送信します。