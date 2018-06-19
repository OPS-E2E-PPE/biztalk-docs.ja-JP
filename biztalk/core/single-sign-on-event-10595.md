---
title: 'シングル サインオン: イベント 10595 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1517478c-7217-4e34-a5cb-ff7deea367ed
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9139eb7479b0a048e2fab197863b42c47f87992a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271266"
---
# <a name="single-sign-on-event-10595"></a>シングル サインオン: イベント 10595
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10595|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_APP_INCOMPLETE_FIELDS|  
|メッセージ テキスト|このアプリケーションのフィールドが入力されていないので、アプリケーションを有効にすることができません。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> 定義したフィールドの数: %2 %r<br /><br /> 作成されたフィールドの数: %3|  
  
## <a name="explanation"></a>説明  
 API レベルでアプリケーションを作成するときに、アプリケーションで定義するフィールド (UserID、Password) を指定しました。 定義した各フィールドは、作成することも必要です。 この警告メッセージは、アプリケーション名、定義されているフィールド数、および作成されたフィールド数の一覧を表示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 定義済みだが作成されていないフィールドを特定し、前の手順に戻ってフィールドを作成します。