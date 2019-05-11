---
title: アダプター ハンドラーを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, handlers [adapters]
- handlers [adapters], creating
- adapters, handlers
ms.assetid: 09569417-dce6-473d-891f-6fd12347bcf0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1e8a8d40beebd93865d657d2a09fc08dc11579a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385532"
---
# <a name="how-to-create-an-adapter-handler"></a>アダプター ハンドラーを作成する方法
送信を作成したり、BizTalk Server 管理コンソールを使用して、アダプターのハンドラーを受信することができます。  
  
> [!NOTE]
>  アダプター ハンドラーを作成するシングル サインオン管理者グループのメンバーがあります。  
  
### <a name="to-create-an-adapter-handler"></a>アダプター ハンドラーを作成するには  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**アダプター**します。  
  
2.  展開したアダプターの一覧で対象にする追加の送信または受信ハンドラーをポイントして、アダプターを右クリックして**新規**、 をクリックし、**送信ハンドラー**送信ハンドラーを作成する**受信ハンドラー**受信ハンドラーを作成します。  
  
3.  **\<ホスト名\>プロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、ホストを選択しますアダプター。ハンドラーが関連付けられます。  
  
4.  アダプターの送信ハンドラーを作成する場合、オプションを選択**既定のハンドラーをこのように**これがこのアダプターの既定の送信ハンドラーかどうか。  
  
5.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [アダプター ハンドラーの作成と削除](../core/creating-and-deleting-adapter-handlers.md)