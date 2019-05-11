---
title: シングル サインオン:イベント 10595 |Microsoft Docs
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
ms.openlocfilehash: 5b6aecfef61ece56075c4eb0c47ba7852380d4c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397849"
---
# <a name="single-sign-on-event-10595"></a>シングル サインオン:イベント 10595
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                             エンタープライズ シングル サインオン                                                                                              |
| 製品バージョン |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    イベント ID     |                                                                                                       10595                                                                                                        |
|  イベント ソース   |                                                                                                       ENTSSO                                                                                                       |
|    コンポーネント    |                                                                                                        なし                                                                                                         |
|  シンボル名  |                                                                                           SSO_WARN_APP_INCOMPLETE_FIELDS                                                                                           |
|  メッセージ テキスト   | フィールドがこの application.%r 不完全なため、アプリケーションを有効にすることはできません。<br /><br /> アプリケーション名: %1 %r<br /><br /> 定義したフィールドの数: % 2 %r<br /><br /> 作成されたフィールドの数: %3 |
  
## <a name="explanation"></a>説明  
 レベル API でアプリケーションを作成、するときに、アプリケーションでは定義フィールド (UserID、Password) の数を指定します。 定義されている各フィールドを作成する必要があります。 この警告メッセージは、アプリケーション名、定義されている場合、フィールドの数と作成されたフィールドの数を示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 定義済みだが作成されていないフィールドを決定し、戻ってそれらを作成します。