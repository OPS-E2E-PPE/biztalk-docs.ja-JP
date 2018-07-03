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
ms.openlocfilehash: 60bb78e2bbf06ff80315bd9bbc2b33346ed18d5d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024168"
---
# <a name="message-types-without-parts-are-not-supported"></a>部分が空のメッセージの種類はサポートされていません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| 製品バージョン |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    イベント ID     |                                                             0                                                             |
|  イベント ソース   |                                                             0                                                             |
|    コンポーネント    |                                                             0                                                             |
|  シンボル名  |                                                             0                                                             |
|  メッセージ テキスト   | 部分が空のメッセージの種類はサポートされていません。 サービスの説明を修正"{0}「メッセージの種類」{1}"、ウィザードを再度実行します。 |
  
## <a name="explanation"></a>説明  
 このエラーは、使用するサービスに、メッセージの種類が定義されていないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 サービスを適切なメッセージの種類に修正し、使用します (使用しようとしている WCF サービスを所有している場合)。 それ以外の場合は、サービス プロバイダーに問い合わせてください。  メッセージの詳細についてで、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [Web メッセージの構築](../core/constructing-web-messages.md)