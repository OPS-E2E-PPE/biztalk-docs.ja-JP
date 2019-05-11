---
title: シングル サインオン:イベント 11022 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c65ca12b-dda8-408b-9512-39df6f8e035b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ee404410a4c1a03b4e910e8f1154edb82e90c11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266551"
---
# <a name="single-sign-on-event-11022"></a>シングル サインオン:イベント 11022
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                                   エンタープライズ シングル サインオン                                                                                                                                                                                    |
| 製品バージョン |                                                                                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                   |
|    イベント ID     |                                                                                                                                                                                             11022                                                                                                                                                                                              |
|  イベント ソース   |                                                                                                                                                                                             ENTSSO                                                                                                                                                                                             |
|    コンポーネント    |                                                                                                                                                                                              なし                                                                                                                                                                                               |
|  シンボル名  |                                                                                                                                                                   SSO_WARN_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED                                                                                                                                                                   |
|  メッセージ テキスト   | 外部パスワード変更が原因で別の外部アカウント changed.%r を<br /><br /> この外部システムのアダプタがマッピング conflicts.%r を許可しないように構成されているため、これは、許可されていません<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> Windows アカウント: % 3 %r<br /><br /> 外部アカウント 1: % 4 %r<br /><br /> 外部アカウント 2: %5 |
  
## <a name="explanation"></a>説明  
 これは、情報メッセージを別の外部アカウントを変更する原因となる外部パスワード変更の失敗を報告します。  
  
## <a name="user-action"></a>ユーザーの操作  
 (このシステムは、マッピングの競合を許可しないように構成されている) ために、変更は行われませんを確認してくださいすぐに、サポート技術情報の承認と、この試行が行われたことです。 場合は、アクションは必要ありません。 それ以外の場合は、変更が開始されると、システム内の安全な場所があることを確認します。