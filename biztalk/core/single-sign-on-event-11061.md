---
title: 'シングル サインオン: イベント 11061 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52fb18e2-4482-4cdb-b8ed-d579a95acd7c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1733e444ecdfdaf54b20beb2de6894ade3466f4c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011331"
---
# <a name="single-sign-on-event-11061"></a>シングル サインオン: イベント 11061
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                     エンタープライズ シングル サインオン                                                                                                                     |
| 製品バージョン |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    イベント ID     |                                                                                                                               11061                                                                                                                               |
|  イベント ソース   |                                                                                                                              ENTSSO                                                                                                                               |
|    コンポーネント    |                                                                                                                                なし                                                                                                                                |
|  シンボル名  |                                                                                                                   SSO_WARN_BAD_PASSWORD_FILTER                                                                                                                    |
|  メッセージ テキスト   | パスワード フィルター文字列が有効ではありません。 パスワード フィルターは使用されません。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> パスワード フィルタ文字列: % 2 %r<br /><br /> 処理されたトークンの数: % 3 %r<br /><br /> 追加データ: % 4 %r<br /><br /> エラー コード: %5 |
  
## <a name="explanation"></a>説明  
 無効なパスワード フィルターが手動で作成されました。 このプロセスの途中で、エラーが発生しました (エラーの場所については、警告テキストの "パスワード フィルター文字列" を参照してください)。  
  
## <a name="user-action"></a>ユーザーの操作  
 パスワード フィルターの作成ウィザードを使用して、パスワード フィルターを作成するを参照してください。[パスワード フィルターを使用する方法](../core/how-to-use-password-filters.md)します。