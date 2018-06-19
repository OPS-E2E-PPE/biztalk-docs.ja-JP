---
title: バッチに対応するアグリーメントが見つかりませんでした |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d1c0480-9a6f-481a-9143-e5a55707c3b5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bce17af0e382a137dc8d55d30705da58dd52301c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237930"
---
# <a name="could-not-find-an-agreement-corresponding-to-batch"></a>バッチに対応するアグリーメントが見つかりませんでした
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|AgreementNotFoundForBatch|  
|メッセージ テキスト|バッチ {0} に対応するアグリーメントが見つかりませんでした。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、バッチの開始/停止時またはバッチ メッセージの処理時に、BizTalk Server がこの ID に対応したバッチを見つけることができなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、指定された ID のバッチが親アグリーメントの [アグリーメントのプロパティ] に存在することを確認します。