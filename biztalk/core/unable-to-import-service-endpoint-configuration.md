---
title: サービス エンドポイント構成をインポートできません。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dae5154-04e2-4d9b-b2b2-85313683fd9e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d33b9b4963b69ed732c16e266300e398d7884035
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994315"
---
# <a name="unable-to-import-service-endpoint-configuration"></a>サービス エンドポイント構成をインポートできません。
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                  サービス エンドポイント構成をインポートできません                   |
  
## <a name="explanation"></a>説明  
 このエラーについては、複数の説明が考えられます。 構成ファイルに無効な文字が含まれている可能性があります。 ルート要素が欠落している可能性があります。 ルート レベルのデータが無効な可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 構成ファイルが正しいかどうかを検証します。 構成ファイル、サービス構成エディターを開く (**svcConfigEditor.exe**) 各プロパティを確認します。