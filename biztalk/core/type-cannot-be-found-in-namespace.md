---
title: 名前空間で型が見つからない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66387fa6-3ba3-499f-99d6-bb0033c68adc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70011a83e5264344a5ef4f30c4525529aa403dce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393771"
---
# <a name="type-cannot-be-found-in-namespace"></a>種類が名前空間に見つかりません
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                エラー:型"{0}「名前空間で見つかったことはできません」{1}"                |
  
## <a name="explanation"></a>説明  
 このエラーは、作成される成果物が型指定された名前空間で見つからないを参照していることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 型が見つからないことが含まれている参照を追加し、(使用しようとしている WCF サービスを所有) 場合は、ウィザードを再度実行します。 それ以外の場合、サービス プロバイダーに問い合わせてください。