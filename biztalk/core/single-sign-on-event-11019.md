---
title: 'シングル サインオン: イベント 11019 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ec07b00-d567-4518-89eb-340e4f92429b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 622badcaa24cfe5a5db45b1d688f2eee3a7f818f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001803"
---
# <a name="single-sign-on-event-11019"></a>シングル サインオン: イベント 11019
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                            エンタープライズ シングル サインオン                                                                                                                                                             |
| 製品バージョン |                                                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                            |
|    イベント ID     |                                                                                                                                                                      11019                                                                                                                                                                       |
|  イベント ソース   |                                                                                                                                                                      ENTSSO                                                                                                                                                                      |
|    コンポーネント    |                                                                                                                                                                       なし                                                                                                                                                                        |
|  シンボル名  |                                                                                                                                                      SSO_PS_WARN_NOT_IN_GROUP_DELETE_FAILED                                                                                                                                                      |
|  メッセージ テキスト   | Windows アカウントがアプリケーションのアプリケーション ユーザー アカウントにないため、マッピングは無効です。 マッピングを削除できませんでした。 マッピングは無視されます。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> アプリケーション ユーザー: % 4 %r<br /><br /> エラー コード: %5 |
  
## <a name="explanation"></a>説明  
 指定された Windows アカウントがアプリケーションのアプリケーション ユーザー アカウントの一部ではなかったか、一時期はそうだったが変更または削除されました。 マッピングは削除されませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 システムのパスワード同期アカウント情報を確認するか、情報が有効であることを確認します。 次にマッピングを再作成します。 マッピングの作成ウィザードを使用すると、無効なマッピング情報のリスクが軽減されることに注意してください。 失敗したマッピングを削除できます。 削除しない場合、失敗したマッピングは無視されます。