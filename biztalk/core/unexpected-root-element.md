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
ms.openlocfilehash: b0e54e0eac7e3f8ae54d23417033388bc493b0ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981635"
---
# <a name="unexpected-root-element"></a>ルート要素が正しくありません
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                              ルート要素が正しくありません                               |
  
## <a name="explanation"></a>説明  
 ヘッダー プロパティにない\<ヘッダー\>...\</headers\>形式。 通常、この状況は InboundHeaders および OutboundCustomHeaders に適用されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 ヘッダー プロパティの形式であることを確認\<ヘッダー\>.\</headers\>します。