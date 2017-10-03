---
title: "シングル サインオン: イベント 10710 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 469dc407-be7a-45a1-bcf5-2ba7060a19e2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1a3dafe3dd5b7dbdf0e5934218af6539427184f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10710"></a>シングル サインオン: イベント 10710
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10710|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_INFO_PS_WIN_CHANGE_DAMPED|  
|メッセージ テキスト|Windows パスワードの変更は抑制されました (重複として検出され、破棄されました)。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: %2 %r<br /><br /> クライアント ユーザー: %3|  
  
## <a name="explanation"></a>説明  
 この情報イベントは、Windows パスワードの変更が重複として検出されたため、破棄されたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
  
-   ユーザーの操作は必要ありません。  
  
 詳細については、次のリソースを参照してください。  
  
-   [パスワード同期](../core/password-synchronization2.md)