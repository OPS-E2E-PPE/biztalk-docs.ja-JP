---
title: シングル サインオン:イベント 10665 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d0de9d0-9b46-4f3a-b796-1ce3de01cf4c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47cd0f957ba835df7f7463a8ee9c33f7b4503eb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397556"
---
# <a name="single-sign-on-event-10665"></a>シングル サインオン:イベント 10665
## <a name="details"></a>詳細  

|                 |                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                               エンタープライズ シングル サインオン                                                |
| 製品バージョン |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    イベント ID     |                                                         10665                                                          |
|  イベント ソース   |                                                         ENTSSO                                                         |
|    コンポーネント    |                                                          該当なし                                                           |
|  シンボル名  |                                                 SSO_WARN_NO_PROPERTIES                                                 |
|  メッセージ テキスト   | パスワード同期アダプターのプロパティの読み取りエラー。 Defaults.%r を使用します。<br /><br /> アダプター: % 1 %r<br /><br /> エラー コード: %2 |

## <a name="explanation"></a>説明  
 この警告イベントは、既定のパスワード同期アダプターのプロパティを読み取り中にエラーがあったことを示します。 各パスワード同期アダプターには、関連付けられている構成プロパティがあります。 これらのプロパティは、SSO 構成ストアに格納され、パスワード同期アダプターが作成されるときに、SSO コマンド ライン ツールまたは SSO 管理 MMC によって作成されます。  あることができます不足しているプロパティ、パスワード同期アダプターは、他の方法で作成された場合、このエラーが発生することができます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

-   パスワード同期アダプターのプロパティを確認します。  

-   パスワード同期アダプターを再作成します。  

## <a name="more-info"></a>詳細情報

- **パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [パスワード同期](../core/password-synchronization2.md)
