---
title: シングル サインオン:イベント 11008 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7e11dbc-7596-45fa-ae54-a6e79498e60e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 367bb91906d659f0848e1745796c639d5e08f0b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306654"
---
# <a name="single-sign-on-event-11008"></a>シングル サインオン:イベント 11008
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                           |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                 エンタープライズ シングル サインオン                                                                 |
| 製品バージョン |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    イベント ID     |                                                                           11008                                                                           |
|  イベント ソース   |                                                                          ENTSSO                                                                           |
|    コンポーネント    |                                                                            なし                                                                            |
|  シンボル名  |                                                                   SSO_WARN_CHECK_GROUP                                                                    |
|  メッセージ テキスト   | グループ メンバーシップ failed.%r を確認してください。<br /><br /> グループ名: %1 %r<br /><br /> アカウント名: % 2 %r<br /><br /> 追加データ: % 3 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 最も可能性の高い原因は、ネットワークの問題、クロス ドメインの使用、またはドメイン コント ローラーのレベルが混在 (システムは、両方のドメイン コント ローラーを使用している場合など、[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]と[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)])。  
  
## <a name="user-action"></a>ユーザーの操作  
 ネットワークの問題がある場合、または任意のクロス ドメインの使用またはレベルのドメイン コント ローラーの混在がある場合、ネットワーク管理者に確認してください。