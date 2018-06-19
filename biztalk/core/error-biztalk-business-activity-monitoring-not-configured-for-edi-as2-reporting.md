---
title: BizTalk ビジネス アクティビティの監視が構成されていない EDI AS2 状態レポートの |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f46c1c8-2771-4b16-8fb1-71952792ac4a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e84301e55cd6fbdcb74467758c7e338e61b727f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241354"
---
# <a name="biztalk-business-activity-monitoring-has-not-been-configured-for-edi-as2-status-reporting"></a>BizTalk ビジネス アクティビティの監視が構成されていない EDI AS2 状態レポート用
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|-|  
|メッセージ テキスト|EDI および AS2 状態レポート用 BizTalk ビジネス アクティビティの監視が構成されていません。 したがって状態レポート機能は無効になります。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ビジネス アクティビティの監視 (BAM) が BizTalk 構成ウィザードを使用して構成されていないため、EDI/AS2 状態レポート機能が有効になっていないことを示します。 EDI/AS2 状態レポート機能を使用するには BAM インフラストラクチャが必要です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、BizTalk 構成ウィザードを実行し、ビジネス アクティビティの監視を構成します。