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
ms.openlocfilehash: 79e9855a3e9719f1a95801683a7b72da9c5ce86b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240296"
---
# <a name="windows-components-may-not-be-installed"></a>Windows コンポーネントがインストールされていない可能性があります。
## <a name="details"></a>詳細  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| 製品バージョン |                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    イベント ID     |                                                                   0                                                                    |
|  イベント ソース   |                                                                   0                                                                    |
|    コンポーネント    |                                                                   0                                                                    |
|  シンボル名  |                                                                   0                                                                    |
|  メッセージ テキスト   | 次の Windows コンポーネントがインストールされていない可能性があります。アプリケーション サーバー -&gt;インターネット インフォメーション サービス (IIS) の&gt;共通ファイル。 |

## <a name="explanation"></a>説明  
 発行はなくインターネット インフォメーション サービス (IIS)、ローカル コンピューターにインストールしようとした場合、このエラーが発生します。  

## <a name="user-action"></a>ユーザーの操作  
 Windows 7 と Windows Vista SP2 では、ローカル IIS のインストールはマシンし、次のように IIS を構成します。  

1. をクリックして**開始**、 をクリックして**コントロール パネルの **、 をクリック**プログラム**します。  

2. クリックして**有効にする Windows 機能のオンとオフを**します。 Windows 機能のウィザードが表示されます。  

3. 追加するには、IIS コンポーネントを確認します。  

   [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]と[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]をローカルの IIS のインストールはマシンし、次のように IIS を構成します。  

4. をクリックして**開始**、 をクリックして**コントロール パネルの **、 をクリック**管理ツール**します。  

5. クリックして**サーバー マネージャー**します。 サーバー マネージャー ウィンドウが表示されます。  

6. クリックして**役割の追加**役割の追加ウィザードが表示されます。  

7. 追加するには、IIS コンポーネントを選択します。
