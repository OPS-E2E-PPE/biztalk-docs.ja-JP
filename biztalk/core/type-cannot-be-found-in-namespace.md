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
ms.openlocfilehash: 8b369b3ce29b989f01f0ea95d6f32a663d7e7bc5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980772"
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
|  メッセージ テキスト   |                エラー: 型"{0}「名前空間で見つかったことはできません」{1}"                |
  
## <a name="explanation"></a>説明  
 このエラーは、作成されたアイテムが、指定した名前空間に存在しない種類を参照していることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 存在しない種類を含む参照を追加し、ウィザードを再実行します (使用する予定の WCF サービスを所有している場合)。 それ以外の場合、サービス プロバイダーに問い合わせてください。