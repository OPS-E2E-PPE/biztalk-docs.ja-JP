---
title: シングル サインオン:イベント 10557 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f29bc394-4c56-4ded-93a1-004afb3a054a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5cd5be8005a1ce13c1ad5f13c580e6e72353b9b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398837"
---
# <a name="single-sign-on-event-10557"></a>シングル サインオン:イベント 10557
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                        エンタープライズ シングル サインオン                                                                                         |
| 製品バージョン |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    イベント ID     |                                                                                                  10557                                                                                                   |
|  イベント ソース   |                                                                                                  ENTSSO                                                                                                  |
|    コンポーネント    |                                                                                                   なし                                                                                                    |
|  シンボル名  |                                                                                   SSO_WARN_USER_NOT_ALLOWED_FOR_GROUPS                                                                                   |
|  メッセージ テキスト   | アプリケーションのユーザーがグループ applications.%r のマッピングを制御する許可されていません<br /><br /> ドメイン名: %1 %r<br /><br /> ユーザー名: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> クライアント ユーザー: %4 |
  
## <a name="explanation"></a>説明  
 ユーザーがアプリケーションには、作成またはグループ アプリケーションに対するマッピングを制御するための十分な特権がありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 このアクティビティは、アプリケーション管理者によって実行する必要があります。