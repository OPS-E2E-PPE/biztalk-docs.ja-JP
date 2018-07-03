---
title: 'シングル サインオン: イベント 10855 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba244f8e-bc61-475f-913c-475ebf1c69ee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2d5914cc119a68c109b883c888b3898bc7db07e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986451"
---
# <a name="single-sign-on-event-10855"></a>シングル サインオン: イベント 10855

|                 |                                                                        |
|-----------------|------------------------------------------------------------------------|
|  製品名   |                       エンタープライズ シングル サインオン                        |
| 製品バージョン |       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]       |
|    イベント ID     |                                 10855                                  |
|  イベント ソース   |                                 ENTSSO                                 |
|    コンポーネント    |                                  なし                                   |
|  シンボル名  |                    ENTSSO_E_PASSWORD_FILTER_FAILED                     |
|  メッセージ テキスト   | パスワード フィルターが失敗したため、資格情報を返すことができません。 |

## <a name="explanation"></a>説明  
 パスワード フィルターが有効ではありません。 最も可能性が高い原因は、フィルターを手動で作成したことです。これは推奨されていません。  

## <a name="user-action"></a>ユーザーの操作  
 フィルターの作成ウィザードを使用して、もう一度パスワード フィルターを作成します。