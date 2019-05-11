---
title: シングル サインオン:イベント 10818 |Microsoft Docs
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
ms.openlocfilehash: aa489e88a3742dfb7acbd1995a6f996bdc58142c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295915"
---
# <a name="single-sign-on-event-10818"></a>シングル サインオン:イベント 10818
## <a name="details"></a>詳細  
  
|                 |                                                                                 |
|-----------------|---------------------------------------------------------------------------------|
|  製品名   |                            エンタープライズ シングル サインオン                            |
| 製品バージョン |           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    イベント ID     |                                      10818                                      |
|  イベント ソース   |                                     ENTSSO                                      |
|    コンポーネント    |                                       なし                                       |
|  シンボル名  |                         ENTSSO_E_AMBIGUOUS_SYNC_FIELDS                          |
|  メッセージ テキスト   | アプリケーションに 2 つのフィールドが必要または同期の 1 つのみのフィールドをマークする必要があります。 |
  
## <a name="explanation"></a>説明  
 複数の 2 つのフィールドがある場合、1 つだけ必要があります指定はパスワードの同期です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このような状況を解決するには、するには、アプリケーションを削除し、再作成するため、これらのガイドラインに従います。