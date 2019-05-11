---
title: シングル サインオン:イベント 10850 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04e2af52-d35b-491a-a983-d80442dd6aef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bd240e9176465c431ca13a5069c3d510f7c2d1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306666"
---
# <a name="single-sign-on-event-10850"></a>シングル サインオン:イベント 10850
## <a name="details"></a>詳細  
  
|                 |                                                                     |
|-----------------|---------------------------------------------------------------------|
|  製品名   |                      エンタープライズ シングル サインオン                      |
| 製品バージョン |     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    イベント ID     |                                10850                                |
|  イベント ソース   |                               ENTSSO                                |
|    コンポーネント    |                                 なし                                 |
|  シンボル名  |                 ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE                 |
|  メッセージ テキスト   | 'Enabled' フラグを指定には、アプリケーションを作成することはできません。 |
  
## <a name="explanation"></a>説明  
 アプリケーションを有効にする前にアプリケーションを作成しての各フィールド (UserID および Password) のフィールド情報を入力する必要があります。 "Enabled"フィールドで、アプリケーションを作成することは既に設定されています。  
  
## <a name="user-action"></a>ユーザーの操作  
 もう一度アプリケーションを作成する (を使用してアプリケーションの作成 API または新しい関連アプリケーション作成ウィザードのいずれか)。 アプリケーションが完了して、フィールドに入力すると、アプリケーションを有効にされます。