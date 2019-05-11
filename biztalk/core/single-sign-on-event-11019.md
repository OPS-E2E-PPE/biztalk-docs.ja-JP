---
title: シングル サインオン:イベント 11019 |Microsoft Docs
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
ms.openlocfilehash: 9b2dbd4c35f8848be7579d897c0426ebf9cfd960
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266614"
---
# <a name="single-sign-on-event-11019"></a>シングル サインオン:イベント 11019
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                            エンタープライズ シングル サインオン                                                                                                                                                             |
| 製品バージョン |                                                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                            |
|    イベント ID     |                                                                                                                                                                      11019                                                                                                                                                                       |
|  イベント ソース   |                                                                                                                                                                      ENTSSO                                                                                                                                                                      |
|    コンポーネント    |                                                                                                                                                                       なし                                                                                                                                                                        |
|  シンボル名  |                                                                                                                                                      SSO_PS_WARN_NOT_IN_GROUP_DELETE_FAILED                                                                                                                                                      |
|  メッセージ テキスト   | アプリケーションのアプリケーション ユーザー アカウントに Windows アカウントがないために、マッピングは無効です。 マッピングを削除できませんでした。 マッピングは ignored.%r 無視されます。<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> アプリケーション ユーザー: % 4 %r<br /><br /> エラー コード: %5 |
  
## <a name="explanation"></a>説明  
 指定された Windows アカウントがこのアプリケーションでのアプリケーション ユーザー アカウントの一部をされなかったか、それが一度に 1 つが変更または削除されました。 マッピングが削除されていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 お使いのシステム パスワード同期アカウント情報を確認し、情報が有効かどうかを確認します。 次のマッピングを再作成します。 無効なマッピング情報のリスクを軽減. マッピングの作成ウィザードを使用することに注意してください。 失敗したマッピングを削除することができます。 削除しない場合は無視されます。