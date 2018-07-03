---
title: 'シングル サインオン: イベント 10818 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ad54646-4285-42e5-a270-d56935742a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 328e4286ed024923ab66e147e806ef5db5065b77
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972435"
---
# <a name="single-sign-on-event-10818"></a>シングル サインオン: イベント 10818
## <a name="details"></a>詳細  
  
|                 |                                                                                 |
|-----------------|---------------------------------------------------------------------------------|
|  製品名   |                            エンタープライズ シングル サインオン                            |
| 製品バージョン |           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    イベント ID     |                                      10818                                      |
|  イベント ソース   |                                     ENTSSO                                      |
|    コンポーネント    |                                       なし                                       |
|  シンボル名  |                         ENTSSO_E_AMBIGUOUS_SYNC_FIELDS                          |
|  メッセージ テキスト   | アプリケーションのフィールドは 2 つであるか、または 1 つのフィールドだけが同期の対象としてマークされている必要があります。 |
  
## <a name="explanation"></a>説明  
 フィールドが 2 つ以上ある場合、パスワードの同期を設定できるのは 1 つだけです。  
  
## <a name="user-action"></a>ユーザーの操作  
 この状況を解決するために、アプリケーションをいったん削除し、これらのガイドラインに沿って再作成する必要があります。