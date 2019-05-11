---
title: 無効なアドレス スキーム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b059289-654e-40d6-a092-2a685e6e10f7
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b2b1a1514c605a40c98dacfd90911f806ddcd2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381489"
---
# <a name="invalid-address-scheme"></a>アドレス スキームが無効です
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                        000                                         |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                  無効なアドレスのスキーム指定してください"{0}"スキーム。                   |
  
## <a name="explanation"></a>説明  
 トランスポート バインディングに定義されている型に一致しないプロトコル スキームを指定したとします。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
1. をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。  
  
2. コンソール ルートで展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。  
  
9. **アドレス (URI)** テキスト ボックスに、アドレスの値が使用されている WCF アダプターの種類と一致していることを確認します。  
  
   また、システム指定のバインディングの種類で、Wcf-custom アダプターを使用する場合の値を確認、**バインドの種類**ボックスの一覧、**バインド**タブ。場合、**バインドの種類**するように構成**customBinding**、アドレスが記載トランスポート バインド要素と一致する必要があります、**バインドの種類**一覧で、 **バインド**タブ。