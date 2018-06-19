---
title: メッセージの種類が、アグリーメントの一部として許可されていません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 829f8230-33b8-4b5f-a56a-d0c1d3a17271
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 979aa43d23d2fca95c244e10cb9d4768d76cf3db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262738"
---
# <a name="message-type-is-not-allowed-as-part-of-the-agreement"></a>メッセージの種類はアグリーメントの一部として使用できません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|TransactionSetNotAllowedDescription|  
|メッセージ テキスト|アグリーメントの一部としては、メッセージの種類 {0} することはできません。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ドキュメントのメッセージの種類がアグリーメントの一部として許可されていないため、BizTalk Server がドキュメントを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、アグリーメントの一部として許可されているメッセージの種類と、許可されていないメッセージの種類を確認します。