---
title: シングル サインオン:イベント 10740 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e8521e7-32af-4a58-8b1a-66ea1d13f1e1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db19b81cb024ff6dfee2196cdefc33f8f977dea9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291756"
---
# <a name="single-sign-on-event-10740"></a>シングル サインオン:イベント 10740
## <a name="details"></a>詳細  

|                 |                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                 エンタープライズ シングル サインオン                                                                  |
| 製品バージョン |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    イベント ID     |                                                                           10740                                                                            |
|  イベント ソース   |                                                                           ENTSSO                                                                           |
|    コンポーネント    |                                                                            該当なし                                                                             |
|  シンボル名  |                                                               SSO_WARN_INVALID_WINDOWS_USER                                                                |
|  メッセージ テキスト   | Windows アカウントがアプリケーション update.%r のため無効です。<br /><br /> アプリケーション名: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> エラー コード: %3 |

## <a name="explanation"></a>説明  
 この警告イベントは、(イベント メッセージで指定された) Windows アカウントがアプリケーションの更新プログラムに対して有効ではないことを示します。 これは、ホスト グループ アプリケーションの Windows アカウントを変更するときに発生します。 ホスト グループ アプリケーションは、シングル サインオンの外部システムから Windows システムに使用されます。 1 つの Windows アカウントに、一連の外部ユーザーをマップできます。 Windows アカウントにマップされますが、アプリケーションのアプリケーション ユーザー フィールドで定義されます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- Windows アカウントの中であることを確認が有効でを使用します。  

- Windows アカウントに適切なプロパティを持つ Windows アカウントを再作成します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期](../core/password-synchronization2.md)
