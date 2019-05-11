---
title: 新しいレジストリ エントリ ページ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 204c547c-ed0e-4a1f-a0b2-ce5da00d9c42
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 146e3032a6b9d3b57b23a6607eb40b61a92bb5bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400071"
---
# <a name="new-registry-entry-page"></a>新しいレジストリ エントリ ページ
図 1 は、指定された Microsoft BizTalk Server の ESB アプリケーションで、既存のエンドポイントの一覧を表示することができます、ESB 管理ポータル新しいレジストリ エントリ ページを示します。  
  
 ![新しいレジストリ エントリ ページ](../esb-toolkit/media/ch8-newregistryentrypage.gif "Ch8 NewRegistryEntryPage")  
  
 **図 1**  
  
 **ESB 管理ポータル新しいレジストリ エントリ ページ**  
  
 次の一覧では、ESB 管理ポータル新しいレジストリ エントリ ページの機能を使用する方法について説明します。  
  
-   種類、状態、および表示するエンドポイントを含む BizTalk アプリケーションを指定するのにには、ページの上部にある 3 つのドロップダウン リストを使用します。  
  
    -   最初の (エンドポイントの種類) ドロップダウン リストで選択**受信場所、送信ポート、** または**のすべてのエンドポイント**します。  
  
    -   2 つ目の (ステータス) ドロップダウン リストで選択**登録されている、NotRegistered、保留中、** または**すべて**します。  
  
    -   3 番目の (BizTalk アプリケーション) ドロップダウン リストでは、現在インストールされている BizTalk アプリケーションの 1 つを選択できます。  
  
-   アプリケーションとエンドポイントの条件を指定するには後、は、一致するエンドポイントの一覧を表示する BizTalk アプリケーションのドロップダウン リストの横にある矢印アイコンをクリックします。  
  
-   エンドポイントの一覧には、エンドポイントの一致の詳細が含まれています。 動的エンドポイントはそれぞれ、一覧には表示およびこのエンドポイントを公開する保留中の要求の詳細を編集できるリンクが含まれます。  
  
-   をクリックして、**詳細の表示**リンクを開くリストのいずれかの行、[レジストリ詳細ページ](../esb-toolkit/registry-details-page.md)要求を変更して、エンドポイントを発行できます。