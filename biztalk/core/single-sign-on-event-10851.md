---
title: シングル サインオン:イベント 10851 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 582b92bf-2833-47cd-b685-1245e870d81d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 172eae8de676cb581dd07b823ab362bf1a2401b5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306631"
---
# <a name="single-sign-on-event-10851"></a>シングル サインオン:イベント 10851
## <a name="details"></a>詳細  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                             エンタープライズ シングル サインオン                                             |
| 製品バージョン |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    イベント ID     |                                                       10851                                                       |
|  イベント ソース   |                                                      ENTSSO                                                       |
|    コンポーネント    |                                                        なし                                                        |
|  シンボル名  |                                     ENTSSO_E_PSADMIN_NO_DIRECT_PASSWORD_SYNC                                      |
|  メッセージ テキスト   | アプリケーションは、'direct password sync' フラグが設定があるため、パスワード同期アダプターに割り当てることはできません。 |
  
## <a name="explanation"></a>説明  
 アプリケーションには、直接パスワード同期とパスワード同期アダプターの両方を使用できません。  
  
## <a name="user-action"></a>ユーザーの操作  
 アプリケーションを確認し、直接パスワード同期が必要かどうかを決定します。フラグが設定のままにする必要があります、その場合は、アプリケーションをパスワード同期アダプターに割り当てるには試行されません。 不要な場合は、フラグをオフにし、必要に応じてパスワード同期アダプターにアプリケーションを割り当てます。