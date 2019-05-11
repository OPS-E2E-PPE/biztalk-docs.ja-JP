---
title: シングル サインオン:イベント 10671 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c5564f-6412-4e83-9bec-03264e992ebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84f3b434cc328b9356e3f5a7db380c92366c210c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397511"
---
# <a name="single-sign-on-event-10671"></a>シングル サインオン:イベント 10671
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                                  エンタープライズ シングル サインオン                                                                                                                                                                                  |
| 製品バージョン |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    イベント ID     |                                                                                                                                                                                            10671                                                                                                                                                                                            |
|  イベント ソース   |                                                                                                                                                                                           ENTSSO                                                                                                                                                                                            |
|    コンポーネント    |                                                                                                                                                                                             該当なし                                                                                                                                                                                             |
|  シンボル名  |                                                                                                                                                                         SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED                                                                                                                                                                          |
|  メッセージ テキスト   | Windows パスワードの変更と同じ外部 system.%r では、複数のアカウントへの変更を、します。<br /><br /> この外部システムのアダプタで構成されているマッピング conflicts.%r を許可するため、これは許可します。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> Windows アカウント: % 3 %r<br /><br /> 外部アカウント 1: % 4 %r<br /><br /> 外部アカウント 2: %5 |

## <a name="explanation"></a>説明  
 この情報イベントでは、Windows パスワードの変更が、同じ外部システムでは、複数のアカウントへの変更を発生はことを示します。  

## <a name="user-action"></a>ユーザーの操作  

-   ユーザー操作は必要ありません。  

## <a name="more-info"></a>詳細情報

- **パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [パスワード同期](../core/password-synchronization2.md)
