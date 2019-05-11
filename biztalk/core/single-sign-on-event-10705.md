---
title: シングル サインオン:イベント 10705 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81456bdd-dfd8-4483-aa76-5ec72350cc70
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e88a77cc05956f50af31094d299b653ce71056f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397289"
---
# <a name="single-sign-on-event-10705"></a>シングル サインオン:イベント 10705
## <a name="details"></a>詳細  

|                 |                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------|
|  製品名   |                                         エンタープライズ シングル サインオン                                          |
| 製品バージョン |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                         |
|    イベント ID     |                                                   10705                                                    |
|  イベント ソース   |                                                   ENTSSO                                                   |
|    コンポーネント    |                                                    該当なし                                                     |
|  シンボル名  |                                          SSO_WARN_PS_NOT_ADAPTER                                           |
|  メッセージ テキスト   | 指定されたアダプターはアダプター アプリケーションではありません。 アプリケーション type.%r を確認してください。<br /><br /> アダプタ: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、指定されたアダプターがアダプター アプリケーションではないことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- SSO 管理 MMC スナップインを使用して、指定のアダプターを右クリックし、プロパティをアプリケーションの種類を確認したり、コマンド ライン ツール ssops を使用 をクリックして--list および ssops-アプリケーションの種類を決定する表示します。  

- アダプターのアプリケーションを設定して、SSO 管理 MMC スナップインまたは ssops-addapp を使用します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)
