---
title: 'シングル サインオン: イベント 10563 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c944cc4-7fe0-41cc-9608-ee954e8222e0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2ff30e245350004d798b0c6c2950b5bab345e77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269714"
---
# <a name="single-sign-on-event-10563"></a>シングル サインオン: イベント 10563
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10563|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_PERFMON_FAILED|  
|メッセージ テキスト|パフォーマンス監視を開始できませんでした。%r<br /><br /> エラー コード: %1|  
  
## <a name="explanation"></a>説明  
 パフォーマンス監視を開始できませんでした。 システムは通常の実行を続行できますが、パフォーマンス監視は使用できません。  
  
## <a name="user-action"></a>ユーザーの操作  
 perfmon ユーティリティのアンインストールと再インストールが必要である可能性があります。