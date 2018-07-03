---
title: 'シングル サインオン: イベント 10740 |Microsoft Docs'
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
ms.openlocfilehash: b9bf7c2cdaae3cffe280035f007cd1b49d2c70c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970059"
---
# <a name="single-sign-on-event-10740"></a>シングル サインオン: イベント 10740
## <a name="details"></a>詳細  

|                 |                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                 エンタープライズ シングル サインオン                                                                  |
| 製品バージョン |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    イベント ID     |                                                                           10740                                                                            |
|  イベント ソース   |                                                                           ENTSSO                                                                           |
|    コンポーネント    |                                                                            N\A                                                                             |
|  シンボル名  |                                                               SSO_WARN_INVALID_WINDOWS_USER                                                                |
|  メッセージ テキスト   | Windows アカウントがアプリケーションの更新について有効ではありません。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> エラー コード: %3 |

## <a name="explanation"></a>説明  
 この警告イベントは、(イベント メッセージに示されている) Windows アカウントがアプリケーションの更新について有効ではないことを示します。 これは、ホスト グループ アプリケーションの Windows アカウントを変更したときに発生する可能性があります。 ホスト グループ アプリケーションは、外部システムから Windows システムへのシングル サインオンに使用されます。 ホスト グループ アプリケーションは、外部ユーザーのセットを 1 つの Windows アカウントにマッピングすることができます。 ホスト グループ アプリケーションがマッピングされる Windows アカウントは、アプリケーションのアプリケーション ユーザー フィールドで定義されます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   

- 使用している Windows アカウントが有効であることを確認します。  

- 正しい Windows アカウントのプロパティを使用して Windows アカウントを再作成します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期](../core/password-synchronization2.md)
