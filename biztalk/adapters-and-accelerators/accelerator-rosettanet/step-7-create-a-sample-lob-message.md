---
title: '手順 7: サンプル LOB メッセージの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, LOB
- loopback tutorial, creating LOB message
- creating, LOB messages
- LOBs, creating messages
ms.assetid: 3023bbc0-5bc4-4e5a-a345-c3253874f0d3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f4bb518217a3fac3f42b60daccbfedc51ee15c0
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855493"
---
# <a name="step-7-create-a-sample-lob-message"></a>手順 7: サンプル LOB メッセージを作成します。
ここでは、LOB アプリケーション ユーティリティを使用して、サンプルの基幹業務 (LOB) メッセージを作成します。  
  
### <a name="to-create-a-sample-message-using-the-lob-application-utility"></a>LOB アプリケーション ユーティリティを使用してサンプル メッセージを作成するには  
  
1.  [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーに移動\<*ドライブ*\>: \Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk フォルダーをダブルクリック**LOBApplication.exe**です。  
  
2.  **LOB Application**  ダイアログ ボックスで、次の操作します。  
  
    |**これを使用してください。**|**これを行う**|  
    |------------------|--------------------|  
    |**Home Profile Name**|型**ホーム**です。|  
    |**取引先名**|型**パートナー**です。|  
    |**PIP の名前**|型**0c1**です。|  
    |**[PIP Version]**|型**R01.02**です。|  
    |**[ファイル名]**|省略記号ボタン (**.**) に移動する\<*ドライブ*:\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobapplication\sampleinstances. 選択 **[0c1 request.xml]** クリックして、ファイルの一覧から**開く**です。|  
    |**メッセージのカテゴリ**|選択**アクション**ドロップダウン リストからです。|  
  
3.  **LOB Application**ダイアログ ボックスで、をクリックして**Submit Message**です。  
  
 LOB アプリケーションは、LOB アプリケーションが生成した元のメッセージをシミュレートして Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] のメッセージを作成します。 メッセージの状態は [Status] ウィンドウで確認できます。  
  
> [!NOTE]
>  サンプル メッセージでは、"HOME" と "PARTNER" のグローバル ビジネス識別子 (GBI) は、それぞれ 123456789 と 987654321 です。 別の GBI を使用する場合は、これらのファイルの内容を変更する必要があります。  
  
## <a name="see-also"></a>参照  
 [手順 8: BTARN データベース内のメッセージの表示](../../adapters-and-accelerators/accelerator-rosettanet/step-8-view-messages-in-the-btarn-databases.md)
