---
title: "シングル サインオン: イベント 11008 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7e11dbc-7596-45fa-ae54-a6e79498e60e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88d2dfa2cfb71d66b43cfaa77b24b1dfce70fd7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11008"></a>シングル サインオン: イベント 11008
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11008|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_CHECK_GROUP|  
|メッセージ テキスト|グループ メンバーシップの確認が失敗しました。%r<br /><br /> グループ名: %1 %r<br /><br /> アカウント名: %2 %r<br /><br /> 追加データ: %3 %r<br /><br /> エラー コード: %4|  
  
## <a name="explanation"></a>説明  
 最も可能性が高い原因は、ネットワークの問題、クロスドメインの使用、またはドメイン コントローラーのレベルの混在 (たとえば、システムが [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] と [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] の両方のドメイン コントローラーを使用している場合) です。  
  
## <a name="user-action"></a>ユーザーの操作  
 ネットワーク管理者と協力して、ネットワークに問題があるかどうか、またはシステムにクロスドメインの使用またはドメイン コントローラーのレベルの混在があるかどうかを確認します。