---
title: シングル サインオン:イベント 10558 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84637b67-09df-4c1e-b9f2-85a738ba0d7a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7161e732fc95aa2fb62ee2ba5e8f188266804206
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398820"
---
# <a name="single-sign-on-event-10558"></a>シングル サインオン:イベント 10558
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                  エンタープライズ シングル サインオン                                                                                   |
| 製品バージョン |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    イベント ID     |                                                                                            10558                                                                                             |
|  イベント ソース   |                                                                                            ENTSSO                                                                                            |
|    コンポーネント    |                                                                                             なし                                                                                              |
|  シンボル名  |                                                                                  SSO_WARN_USER_OWN_MAPPINGS                                                                                  |
|  メッセージ テキスト   | アプリケーションのユーザーが独自の mappings.%r を制御するのみ使用できます。<br /><br /> ドメイン名: %1 %r<br /><br /> ユーザー名: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> クライアント ユーザー: %4 |
  
## <a name="explanation"></a>説明  
 試行を別のユーザーのマッピングを制御するアプリケーションのユーザーによってしました。 これは許可されていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 マッピングは、それらの特定のマッピングに対してアプリケーションのユーザーによってのみ制御できます。