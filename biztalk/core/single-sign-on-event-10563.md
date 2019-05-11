---
title: シングル サインオン:イベント 10563 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c944cc4-7fe0-41cc-9608-ee954e8222e0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b735a435a076b873b8462f3b794012f731956ad1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398807"
---
# <a name="single-sign-on-event-10563"></a>シングル サインオン:イベント 10563
## <a name="details"></a>詳細  
  
|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  製品名   |                      エンタープライズ シングル サインオン                       |
| 製品バージョン |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    イベント ID     |                                10563                                 |
|  イベント ソース   |                                ENTSSO                                |
|    コンポーネント    |                                 なし                                  |
|  シンボル名  |                       SSO_WARN_PERFMON_FAILED                        |
|  メッセージ テキスト   | パフォーマンスの監視を start.%r できませんでした。<br /><br /> エラー コード: %1 |
  
## <a name="explanation"></a>説明  
 パフォーマンスの監視を開始できませんでした。 システムは引き続き通常どおりに実行がパフォーマンスの監視は使用できません。  
  
## <a name="user-action"></a>ユーザーの操作  
 アンインストールして、perfmon ユーティリティを再インストールする必要がある場合があります。