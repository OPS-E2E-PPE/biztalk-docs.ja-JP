---
title: アダプター ハンドラーとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- handlers [adapters]
- adapters, handlers
- handlers [adapters], about handlers
ms.assetid: 4d1afa39-6320-467f-a7e8-f5f18236648e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09ef44c037b175497dfb6c1fb30ea9dd9fb0a43d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379690"
---
# <a name="what-is-an-adapter-handler"></a>アダプター ハンドラーとは何ですか。
アダプター ハンドラーは、アダプター コードを実行する BizTalk ホストのインスタンスです。 指定の送信または受信アダプターのハンドラーをするときに、アダプター コードのコンテキストで実行するホスト インスタンスを指定します。 アダプター ハンドラーは、アダプタを実行し、アダプターの特定のインスタンスのプロパティが含まれています。 既定の BizTalk Server の構成がインストールされているアダプターのすべてのアダプター ハンドラーを作成しますが、負荷分散のための追加のアダプタ ハンドラを作成するかを特定のアダプター ハンドラーのプロセスの分離を提供することがあります。  
  
 アダプター ハンドラーは、BizTalk ホスト インスタンスにバインドされ、BizTalk ホスト インスタンスが BizTalk server にバインドされます。 そのため、負荷分散アダプターが BizTalk サーバー間で処理する場合、BizTalk グループに別の BizTalk server を追加する必要があります。 プロセスの分離するために、追加のアダプタ ハンドラを作成する場合、BizTalk グループに BizTalk server を追加する必要はありません。  
  
 アダプター ハンドラーを実行する新しいホスト インスタンスを作成する必要がある場合は、まずホストを作成し、BizTalk server のいずれかで実行するには、そのホストのインスタンスを作成する必要があります。 詳細については、次を参照してください。[新しいホストを作成する方法](../core/how-to-create-a-new-host.md)と[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)します。  
  
 HTTP および SOAP アダプターの受信ハンドラーを除くすべてのアダプター ハンドラーは、インプロセス ホストで実行するように構成する必要があります。 HTTP および SOAP アダプターの受信ハンドラー、分離ホストでのみ実行できます。  
  
## <a name="see-also"></a>参照  
 [アダプター ハンドラーの作成と削除](../core/creating-and-deleting-adapter-handlers.md)