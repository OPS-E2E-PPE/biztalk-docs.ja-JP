---
title: シングル サインオン:イベント 10673 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa1d572a-1e9f-496e-a219-852e7d9228d5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d6481684fdb53aed156703a52e472c3fe1f06d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397496"
---
# <a name="single-sign-on-event-10673"></a>シングル サインオン:イベント 10673
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                        エンタープライズ シングル サインオン                                                                                                                                                                         |
| 製品バージョン |                                                                                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                        |
|    イベント ID     |                                                                                                                                                                                  10673                                                                                                                                                                                   |
|  イベント ソース   |                                                                                                                                                                                  ENTSSO                                                                                                                                                                                  |
|    コンポーネント    |                                                                                                                                                                                   該当なし                                                                                                                                                                                    |
|  シンボル名  |                                                                                                                                                                SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED                                                                                                                                                                 |
|  メッセージ テキスト   | 外部パスワード変更が発生する 1 つ以上の Windows account.%r への変更<br /><br /> この外部システムのアダプタで構成されているマッピング conflicts.%r を許可するため、これは許可します。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 外部アカウント: % 3 %r<br /><br /> Windows アカウント 1: % 4 %r<br /><br /> Windows アカウント 2: %5 |

## <a name="explanation"></a>説明  
 この情報イベントは、外部パスワード変更は 1 つ以上の Windows アカウントへの変更が発生することを示します。  

## <a name="user-action"></a>ユーザーの操作  

-   ユーザー操作は必要ありません。  

## <a name="more-info"></a>詳細情報

- [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)  

- **パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [パスワード同期](../core/password-synchronization2.md)
