---
title: '付録 b: PeopleSoft アプリケーションの使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PeopleSoft, using
- using PeopleSoft application
ms.assetid: 36475836-1d23-4bb4-a3c1-cdd3fff28476
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbe0bba08421360364fb668be9ae4d980d7a54d8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964144"
---
# <a name="appendix-b-using-the-peoplesoft-application"></a>付録 b: PeopleSoft アプリケーションの使用
このセクションでは、オーケストレーションのテストに役立つ、PeopleSoft のさまざまな領域の使用法について説明します。  
  
 受信ポートとして PeopleSoft を使用している場合、PeopleTools を使用して XML ドキュメントを作成できます。 PeopleSoft を操作するために何も特別なものは必要ありません。 イベントのできる必要がありますへのアクセス、 **http\\\\:\<ホスト\>:\<ポート\>** PeopleSoft からイベントをリッスンします。 ホストやポートを使用できない場合は、PeopleSoft Integration Broker を構成することによって、特定の HTTP ホストおよびポートを設定できます。  
  
 完了、PeopleSoft のテストの受信ポートを[を生成する XML、または PeopleSoft のスキーマ](../core/generating-xml-or-schema-in-peoplesoft.md)PeopleSoft 環境で何かを変更して PeopleSoft イベントをトリガーする方法について説明します。 この変更により XML ファイルが有効になり、ファイルはオーケストレーションで監視対象として設定したフォルダーに送信されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [PeopleSoft での XML またはスキーマの生成](../core/generating-xml-or-schema-in-peoplesoft.md)  
  
-   [PeopleSoft の HTTP ホストとポートを作成する](../core/creating-a-peoplesoft-http-host-and-port.md)