---
title: スキームが無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb3e70a-d23c-45e9-bde5-edae6731e58a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 063c60ed07d89429f14f7ed3b7c090cdc0bac033
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008163"
---
# <a name="invalid-scheme"></a>スキームが無効です
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                  スキームが無効です。スキームを指定してください"{0}「または」{1}"                   |
  
## <a name="explanation"></a>説明  
 次のいずれかが発生しました。 URI (uniform リソース識別子) フィールドに指定されているアドレスが http:// または https:// で開始する必要があります。 または、スキームが、トランスポート バインディング要素の実装で指定されているスキームと一致しません。  
  
## <a name="user-action"></a>ユーザーの操作  
 http:// または https:// から始まる有効なプロキシ アドレスの URI を入力します