---
title: "シングル サインオン: イベント 10818 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ad54646-4285-42e5-a270-d56935742a95
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be2c40fa5da46f5045b55c815be9f6f8048cda67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10818"></a>シングル サインオン: イベント 10818
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10818|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_AMBIGUOUS_SYNC_FIELDS|  
|メッセージ テキスト|アプリケーションのフィールドは 2 つであるか、または 1 つのフィールドだけが同期の対象としてマークされている必要があります。|  
  
## <a name="explanation"></a>説明  
 フィールドが 2 つ以上ある場合、パスワードの同期を設定できるのは 1 つだけです。  
  
## <a name="user-action"></a>ユーザーの操作  
 この状況を解決するために、アプリケーションをいったん削除し、これらのガイドラインに沿って再作成する必要があります。