---
title: BizTalk エンドポイントを公開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8e8cc81-c6c7-4269-81e3-8725082a0c98
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f24dbdb80e284602d6c02ce7234f51c7c7f94048
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301847"
---
# <a name="publishing-biztalk-endpoints"></a>BizTalk エンドポイントを公開します。
ESB 管理ポータルを使用して、作成して、現在構成されている Universal Description, Discovery, and Integration (UDDI) サーバーへのエントリを発行することができます。  
  
### <a name="to-publish-a-microsoft-biztalk-server-endpoint-into-the-current-uddi-server"></a>現在の UDDI サーバーに Microsoft BizTalk Server のエンドポイントを公開するには  
  
1.  ポイントして、**レジストリ**ポータルのメイン メニューで、タブをクリックして**新しいレジストリ エントリ**を開く、[新しいレジストリ エントリ ページ](../esb-toolkit/new-registry-entry-page.md)。  
  
2.  ページのドロップダウン リストを使用して、エンドポイントが存在する場所をエンドポイントの種類、状態、およびアプリケーションでフィルター処理します。  
  
3.  UDDI 登録要求を発行するエンドポイントの横にある矢印アイコンをクリックします。  
  
4.  管理者がエンドポイントの自動発行を有効な場合、ポータルは自動的に UDDI サーバーに新しいエントリを公開します。  
  
5.  管理者は、エンドポイントの自動発行を有効になっていませんでは、管理者が承認または要求を拒否するまで、要求がキューに残ります。