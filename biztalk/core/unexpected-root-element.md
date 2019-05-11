---
title: 予期しないルート要素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecccf57e-9295-4a6d-95b6-efec662478cf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a34b014015d97a6dfa9dc11345e47480f055a237
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399493"
---
# <a name="unexpected-root-element"></a>予期しないルート要素
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                              予期しないルート要素                               |
  
## <a name="explanation"></a>説明  
 ヘッダー プロパティにない\<ヘッダー\>...\</headers\>形式。 通常、このような状況は InboundHeaders および OutboundCustomHeaders に適用されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 ヘッダー プロパティの形式であることを確認\<ヘッダー\>.\</headers\>します。