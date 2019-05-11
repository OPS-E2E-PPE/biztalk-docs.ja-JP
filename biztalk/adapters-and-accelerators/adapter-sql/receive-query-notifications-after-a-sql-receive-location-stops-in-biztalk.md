---
title: BizTalk Server を使用した SQL でクエリ通知した後、受信場所のブレーク ダウンを受け取る |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e70fa4c2-d81b-4eb0-a23d-871b64c881e6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a40ea3ecad02e248d9c4f993be53c51434751b56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368533"
---
# <a name="receive-query-notifications-after-a-receive-location-breakdown-in-sql-using-biztalk-server"></a>BizTalk Server を使用した SQL でクエリ通知した後、受信場所のブレーク ダウンを受け取る
EMPLOYEE テーブルに変更されたときに、データベース変更通知のメッセージを受信する BizTalk アプリケーションが存在するシナリオを検討してください。 一部として、受信場所が構成されている場合、BizTalk アプリケーションが分割し同時に EMPLOYEE テーブルにレコードが追加される、最近追加されたレコードの通知が届きません。 わからない、受信場所が再度使用可能です。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティを公開します**NotifyOnListenerStart**、受信場所が回復した通知を受け取る構成できます。 次の値を指定することができます、 **NotifyOnListenerStart**プロパティをバインドします。  
  
- このプロパティを設定**True**、受信場所に回復するとすぐに受信場所が使用可能な通知の通知を受信します。  
  
- このプロパティを設定**False**、受信場所が回復、受信場所の回復後通知通知を受信しません。  
  
  既定値は**True**します。  
  
## <a name="configuring-the-sql-adapter-behavior"></a>SQL アダプターの動作を構成します。  
 いずれの方法には、メタデータを生成するときに、または BizTalk アプリケーションを構成するときに、特定のタスクを実行する必要はありません。 のみを設定する必要があります、 **NotifyOnListenerStart**適宜 Wcf-custom または WCF SQL の受信場所にプロパティをバインドします。 BizTalk アプリケーションを作成する」の説明に従って、同じ一連のタスクを実行する必要があります[受信クエリ通知増分 BizTalk Server を使用して SQL から](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)します。 ただし、使用して BizTalk アプリケーションを構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の値の変更を試みることができます、 **NotifyOnListenerStart**プロパティをバインドし、2 つの構成の違いを確認します。  
  
 次の図は、通知の値に基づいて受信方法を示して、 **NotifyOnListenerStart**プロパティをバインドします。  
  
 ![通知の SQL アダプターを構成](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")  
  
 最初のシナリオで注意ときに、 **NotifyOnListenerStart**に設定されている**true**レコードがデータベース テーブルに挿入されるは、受信場所がダウンしていたときに、アダプターにのみ送信すると、通知メッセージ受信場所に戻ったときにします。 アダプターでは、受信場所がダウンしていた間に挿入されたレコードを処理する操作は実行されません。 アダプターのクライアントは、受信場所がダウンしていた間に挿入されたレコードを処理するには、そのアプリケーション内で関連するロジックを実装する必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して SQL クエリ通知を受け取る](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)