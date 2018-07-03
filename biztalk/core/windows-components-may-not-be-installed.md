---
title: Windows コンポーネントがインストールされていない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc78ac0a-ee21-4633-afb3-1357efd29903
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d61ded5b2ddb077ff0851c20d673fad4f9de9d26
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975507"
---
# <a name="windows-components-may-not-be-installed"></a>Windows コンポーネントがインストールされていない可能性があります
## <a name="details"></a>詳細  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| 製品バージョン |                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    イベント ID     |                                                                   0                                                                    |
|  イベント ソース   |                                                                   0                                                                    |
|    コンポーネント    |                                                                   0                                                                    |
|  シンボル名  |                                                                   0                                                                    |
|  メッセージ テキスト   | 次の Windows コンポーネントがインストールされていない可能性があります。 アプリケーション サーバー -&gt;インターネット インフォメーション サービス (IIS) の&gt;共通ファイル。 |

## <a name="explanation"></a>説明  
 このエラーは、インターネット インフォメーション サービス (IIS) がローカル コンピューターにインストールされていない状態で公開が試行されたときに発生します。  

## <a name="user-action"></a>ユーザーの操作  
 Windows 7 および Windows Vista SP2 の場合、IIS をローカル コンピューターにインストールし、次のように IIS を構成します。  

1. をクリックして**開始**、 をクリックして**コントロール パネルの **、 をクリック**プログラム**します。  

2. クリックして**有効にする Windows 機能のオンとオフを**します。 Windows の機能ウィザードが表示されます。  

3. IIS コンポーネントを追加するために、IIS コンポーネントにチェックマークを付けます。  

   [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] および [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] の場合、IIS をローカル コンピューターにインストールし、次のように IIS を構成します。  

4. をクリックして**開始**、 をクリックして**コントロール パネルの **、 をクリック**管理ツール**します。  

5. クリックして**サーバー マネージャー**します。 サーバー マネージャー ウィンドウが表示されます。  

6. クリックして**役割の追加**役割の追加ウィザードが表示されます。  

7. IIS コンポーネントを追加するために、IIS コンポーネントを選択します。
