---
title: メッセージの種類の部分はサポートされていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0bfb042-feda-4282-a7fa-c13be4ff6254
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef2ef118aab93f10d766aeaf34af74a23908822
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394535"
---
# <a name="message-types-without-parts-are-not-supported"></a>メッセージの種類の部分はサポートされていません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| 製品バージョン |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    イベント ID     |                                                             0                                                             |
|  イベント ソース   |                                                             0                                                             |
|    コンポーネント    |                                                             0                                                             |
|  シンボル名  |                                                             0                                                             |
|  メッセージ テキスト   | メッセージの種類の部分は、サポートされていません。 サービスの説明を修正"{0}「メッセージの種類」{1}"、ウィザードを再度実行します。 |
  
## <a name="explanation"></a>説明  
 このエラーは、使用しようとするサービスに定義されているメッセージ型がないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 適切なメッセージの種類、サービスを修正して、(使用しようとしている WCF サービスを所有) 場合に使用する再試行してください。 それ以外の場合、サービス プロバイダーに問い合わせてください。  メッセージの詳細についてで、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [Web メッセージの構築](../core/constructing-web-messages.md)