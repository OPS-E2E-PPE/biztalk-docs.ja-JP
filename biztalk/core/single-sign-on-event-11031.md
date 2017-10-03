---
title: "シングル サインオン: イベント 11031 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ecd24c2-e251-4eb9-b3ca-ec0f095bb23a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aec5ae3a128da8a13379c574ddd2dba3c1065f79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11031"></a>シングル サインオン: イベント 11031
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11031|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_INFO_PS_WIN_CHANGE_INVALID_MAPPING|  
|メッセージ テキスト|Windows パスワードが変更されています。 この Windows アカウントのマッピングが検出されましたが、有効ではなくなっているために無視されました。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: %2 %r<br /><br /> アプリケーション: %3 %r<br /><br /> 外部アカウント: %4 %r<br /><br /> クライアント ユーザー: %5|  
  
## <a name="explanation"></a>説明  
 Windows アカウントが存在しており、有効である可能がありますが、アプリケーション ユーザー アカウントに含まれていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 マッピングを削除し、再作成してみます。