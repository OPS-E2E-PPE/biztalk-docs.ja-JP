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
ms.openlocfilehash: b29ee2fb5361aed12c7f90a094e3abeb7296e495
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381270"
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
 次のいずれかが発生しました。 URI (uniform リソース識別子) フィールドに指定されているアドレスが http:// または https:// で開始する必要があります。 または、スキーム、トランスポート バインド要素の実装で指定されているものと一致しません。  
  
## <a name="user-action"></a>ユーザーの操作  
 有効なプロキシ アドレス http:// または https:// で始まる URI を入力します。