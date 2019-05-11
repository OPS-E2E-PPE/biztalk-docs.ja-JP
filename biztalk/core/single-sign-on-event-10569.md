---
title: シングル サインオン:イベント 10569 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e051a84-51c1-4e63-be55-6278a1d17c5e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21e3c6e7650e61af9811cd58542a7a4d2b6204af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398761"
---
# <a name="single-sign-on-event-10569"></a>シングル サインオン:イベント 10569
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                       エンタープライズ シングル サインオン                                                                                        |
| 製品バージョン |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    イベント ID     |                                                                                                 10569                                                                                                  |
|  イベント ソース   |                                                                                                 ENTSSO                                                                                                 |
|    コンポーネント    |                                                                                                  なし                                                                                                   |
|  シンボル名  |                                                                                    SSO_WARN_NO_UPDATE_BY_APP_ADMIN                                                                                     |
|  メッセージ テキスト   | アプリケーション管理者アカウントは、アプリケーション Administrator.%r 変更ことはできません。<br /><br /> アプリケーション名: %1 %r<br /><br /> アプリケーション管理者: % 2 %r<br /><br /> エラー コード: %3 |
  
## <a name="explanation"></a>説明  
 アプリケーション管理者アカウントには、アプリケーション管理者を変更できません。  
  
## <a name="user-action"></a>ユーザーの操作  
 SSO 関連アプリケーション管理者、またはをアプリケーション管理者アカウントを変更するためにする必要があります。