---
title: "予期しないルート要素 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecccf57e-9295-4a6d-95b6-efec662478cf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5119b9b896b3b37b24b9b3151c5e11664dda8774
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unexpected-root-element"></a>ルート要素が正しくありません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|ルート要素が正しくありません|  
  
## <a name="explanation"></a>説明  
 ヘッダー プロパティに含まれていない\<ヘッダー >...\</headers > の形式です。 通常、この状況は InboundHeaders および OutboundCustomHeaders に適用されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 ヘッダー プロパティの形式であることを確認\<ヘッダー >.\</headers >。