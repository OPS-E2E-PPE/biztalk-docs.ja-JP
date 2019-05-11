---
title: 無効なアドレスの長さ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8e16eb6-e77e-4361-ac91-0730004c4433
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c23c8c20dba45957cb338b588e16013a01626b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381486"
---
# <a name="invalid-address-length"></a>アドレスの長さが無効です
## <a name="details"></a>詳細  

|                 |                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------|
|  製品名   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]      |
| 製品バージョン |                 [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                  |
|    イベント ID     |                                              0                                              |
|  イベント ソース   |                                              0                                              |
|    コンポーネント    |                                              0                                              |
|  シンボル名  |                                              0                                              |
|  メッセージ テキスト   | 無効なアドレスの長さ。指定されたアドレスの長さは{0}文字制限は{1}文字 |

## <a name="explanation"></a>説明  
 WCF トランスポートの 255 文字の最大長を超えるアドレスを指定するとします。 これは、WCF ではなく、BizTalk Server によって課される制限です。  

## <a name="user-action"></a>ユーザーの操作  
 有効なアドレスを構成するのにには、次の手順を使用します。  

#### <a name="to-configure-a-valid-address"></a>有効なアドレスを構成するには  

1. をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。  

2. コンソール ルートで展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。  

3. アプリケーションを見つけて、トランスポートを特定します。  

4. トランスポート名を右クリックします。  

5. **[プロパティ]** をクリックします。  

6. ポート**型**一覧で、適切なポートを選択します。  

7. をクリックして**構成**です。  

8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。  

9. **アドレス (URI)** テキスト ボックスに、アドレスが 255 文字の最大の長さを超えていないことを確認します。
