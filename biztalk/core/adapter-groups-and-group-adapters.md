---
title: アダプター グループとグループ アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e0a9423-99dd-4474-afa1-fd8e1d074cd1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33cba4d210f79072f5f36a0a47e8546b2d2db265
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361450"
---
# <a name="adapter-groups-and-group-adapters"></a>アダプター グループとグループ アダプター
*アダプター グループ*を収集して、一連のアダプターの整理に使用できる管理メカニズムです。 これに対し、*グループ アダプター*はアダプター グループ内のすべてのアダプター サービスを提供するコンポーネントです。 たとえば、アダプターのセットを記述する場合があります TCP/IP 経由でパスワード同期を送信する同じ COM コンポーネントを使用します。 サービスのすべてのコンポーネントは、グループ アダプターと呼ばれますが、一連のアダプターは、アダプター グループと呼び出されます。 構成ストアでは、アダプター グループがについて説明します。 使用して、情報と、アダプター グループの更新プログラムを取得することができます`ISSOPSAdapter.ReceiveNotification`します。  
  
 グループ アダプターには、アダプター グループと同じ名前があります。 名前付けの制限、以外は、グループ アダプターは通常のアダプターと同じでもそれ以外の場合。 たとえば、グループ アダプターが、構成ファイルの説明に従って、個別のアクセス グループおよび構成のプロパティを持つことができます。 グループ アダプターは、アダプター グループに含まれるアダプターと同じコンピューターに最も可能性があります。 ただし、これは現在適用されません。 同様に、同じコンピューター上に存在する同じアダプター グループ内のすべてのアダプターが期待できます。  
  
 使用して`ISSOPSAdapter.InitializeAdapter`、アクセスして、スタートアップ時に、グループ アダプターを初期化します。 グループ アダプターを初期化するときに、システムは現在のシステムでアダプター グループ内のすべてのアダプターのグループ アダプターに通知します。 さらに、システム通知を送信、グループ アダプターにいつでも、アダプターは追加、削除、有効な場合、または、アダプター グループに無効になっています。 ただし、グループ アダプターはパスワード変更通知を受信しません。  
  
 アダプター グループとグループ アダプターは、管理ツールを使用して省略可能です。  
  
## <a name="see-also"></a>参照  
 [パスワード同期アダプター](../core/password-sync-adapters.md)