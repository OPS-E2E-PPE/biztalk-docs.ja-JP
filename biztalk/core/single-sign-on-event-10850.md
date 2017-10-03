---
title: "シングル サインオン: イベント 10850 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04e2af52-d35b-491a-a983-d80442dd6aef
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94e9bef6d104b8da3c41d295005a7a274a1d2610
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10850"></a>シングル サインオン: イベント 10850
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10850|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE|  
|メッセージ テキスト|'enabled' フラグを指定してアプリケーションを作成することはできません。|  
  
## <a name="explanation"></a>説明  
 アプリケーションを有効にするには、アプリケーションを作成し、アプリケーションの各フィールド (UserID および Password) にフィールド情報を入力する必要があります。 "enabled" フィールドを設定済みの状態でアプリケーションを作成することはできません。  
  
## <a name="user-action"></a>ユーザーの操作  
 アプリケーション作成 API または関連アプリケーションの新規作成ウィザードを使用して、もう一度アプリケーションを作成します。 アプリケーションが完成し、フィールドに情報を入力してから、アプリケーションを有効にします。