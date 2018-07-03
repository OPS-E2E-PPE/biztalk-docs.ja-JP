---
title: 受信場所のブレーク ダウン後の Oracle データベース変更通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22ad6da2-2979-4158-b1d1-d54095223af9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96e10d45158dc3ce1f07032a182ce8088f90ac92
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988235"
---
# <a name="receive-oracle-database-change-notifications-after-a-receive-location-breakdown"></a>受信場所のブレーク ダウン後に、Oracle データベース変更通知を受信します。
ACCOUNTACTIVITY テーブルに変更されたときに、データベース変更通知のメッセージを受信する BizTalk アプリケーションが存在するシナリオを検討してください。 一部として、受信場所が構成されている場合、BizTalk アプリケーションが分割し同時に ACCOUNTACTIVITY テーブルにレコードが追加、最近追加されたレコードの通知は受け取りません。 わからない、受信場所が再度使用可能です。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを公開します**NotifyOnListenerStart**、受信場所が回復した通知を受け取る構成できます。 次の値を指定することができます、 **NotifyOnListenerStart**プロパティをバインドします。  
  
- このプロパティを設定**True**、受信場所に回復するとすぐに受信場所が使用可能な通知の通知を受信します。  
  
- このプロパティを設定**False**、受信場所が回復、受信場所の回復後通知通知を受信しません。  
  
  既定値は**True**します。  
  
## <a name="configuring-the-oracle-database-adapter-behavior"></a>Oracle データベース アダプターの動作を構成します。  
 いずれの方法には、メタデータを生成するときに、または BizTalk アプリケーションを構成するときに、特定のタスクを実行する必要はありません。 のみを設定する必要があります、 **NotifyOnListenerStart**適宜 Wcf-custom または Wcf-oracledb で受信場所にプロパティをバインドします。 BizTalk アプリケーションを作成する」の説明に従って、同じ一連のタスクを実行する必要があります[受信 Oracle データベース変更通知増分を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)します。 ただし、使用して BizTalk アプリケーションを構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の値を変更するをお試しください**NotifyOnListenerStart**プロパティをバインドし、2 つの構成の違いを確認します。  
  
 次の図は、通知の値に基づいて受信方法を示して、 **NotifyOnListenerStart**プロパティをバインドします。  
  
 ![通知の SQL アダプターを構成](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")  
  
 最初のシナリオで注意ときに、 **NotifyOnListenerStart**に設定されている**True**レコードがデータベース テーブルに挿入されるは、受信場所がダウンしていたときに、アダプターにのみ送信すると、受信場所が動作するときの通知メッセージです。 アダプターでは、受信場所がダウンしていた間に挿入されたレコードを処理する操作は実行されません。 アダプターのクライアントは、受信場所がダウンしていた間に挿入されたレコードを処理するには、そのアプリケーション内で関連するロジックを実装する必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を使用して Oracle データベースの変更通知を受け取る](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)