---
title: アダプタ ハンドラについて | Microsoft Docs
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
ms.openlocfilehash: 7c8a1b60661427776dd4e35ffce27bf120bf94a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289306"
---
# <a name="what-is-an-adapter-handler"></a>アダプタ ハンドラについて
アダプタ ハンドラとは、アダプタ コードを実行する BizTalk ホストのインスタンスです。 アダプタの送信ハンドラまたは受信ハンドラを指定するとき、アダプタ コードが実行されるコンテキストとなるホスト インスタンスを指定します。 アダプタ ハンドラには、アダプタを実行する役割があり、アダプタの特定のインスタンスのプロパティが含まれています。 既定の BizTalk Server 構成では、インストールされているすべてのアダプタに対してアダプタ ハンドラが作成されますが、特定のアダプタ ハンドラへの負荷分散やプロセス分離のために、追加のアダプタ ハンドラを作成することができます。  
  
 アダプタ ハンドラは BizTalk ホスト インスタンスにバインドされ、BizTalk ホスト インスタンスは BizTalk Server にバインドされます。 そのため、アダプタの処理の負荷を複数の BizTalk Server 間で分散する場合は、別の BizTalk Server を BizTalk グループに追加する必要があります。 プロセス分離のために追加のアダプタ ハンドラを作成する場合は、BizTalk グループに BizTalk Server を追加する必要はありません。  
  
 アダプタ ハンドラを実行する新しいホスト インスタンスを作成する場合は、最初にホストを作成してから、BizTalk Server のいずれかで実行する、そのホストのインスタンスを作成する必要があります。 詳細については、次を参照してください。[を新しいホストを作成する方法](../core/how-to-create-a-new-host.md)と[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)です。  
  
 HTTP アダプタおよび SOAP アダプタの受信ハンドラを除くすべてのアダプタ ハンドラは、インプロセス ホストで実行されるように構成する必要があります。 HTTP アダプタおよび SOAP アダプタの受信ハンドラは分離ホストでのみ実行できます。  
  
## <a name="see-also"></a>参照  
 [作成して、アダプター ハンドラーを削除します。](../core/creating-and-deleting-adapter-handlers.md)