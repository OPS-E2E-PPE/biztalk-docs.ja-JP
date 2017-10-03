---
title: "メッセージ部分はサポートされていないなしの種類 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0bfb042-feda-4282-a7fa-c13be4ff6254
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e3e6cc0f5d4a2ae18ff6bcb5fa0dc8ef605d730
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-types-without-parts-are-not-supported"></a>部分が空のメッセージの種類はサポートされていません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|部分が空のメッセージの種類はサポートされていません。 サービスの説明"0"} のメッセージの種類「{1}」を解決し、ウィザードを再実行します。|  
  
## <a name="explanation"></a>説明  
 このエラーは、使用するサービスに、メッセージの種類が定義されていないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 サービスを適切なメッセージの種類に修正し、使用します (使用しようとしている WCF サービスを所有している場合)。 それ以外の場合は、サービス プロバイダーに問い合わせてください。  メッセージの詳細については、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [Web メッセージの構築](../core/constructing-web-messages.md)