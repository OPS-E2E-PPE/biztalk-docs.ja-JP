---
title: PIP からの整形式メッセージ インスタンスを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message templates
- PIPs, message templates
ms.assetid: fed3698c-25d9-40ca-878a-60171f425bec
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 040fee5fab56a1e54b777fc7548b8ff28e5b07ec
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960688"
---
# <a name="creating-a-well-formed-message-instance-from-a-pip"></a>PIP からの整形式メッセージ インスタンスを作成します。
ここでは、整形式のメッセージ インスタンスを生成する方法を説明します。 PIP (Partner Interface Process) からメッセージ インスタンスのテンプレートを生成できます。 その後、データを追加する前に、それが整形式になるように、そのテンプレートを変更する必要があります。  
  
### <a name="to-generate-a-message-instance-template-from-the-pip"></a>PIP からメッセージ インスタンス テンプレートを生成するには  
  
1.  開始**Microsoft Visual Studio 2012**です。  
  
2.  **ファイル** メニューのをポイント**開く**、順にクリック**プロジェクト**です。  
  
3.  検索\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanetsdk \schemas に移動をクリックして**RNPIPs.btproj**、クリックして**開く**です。  
  
4.  ソリューション エクスプ ローラーで、 **Rnpip**、し、インスタンスを作成する PIP を右クリックします。  
  
5.  をクリックして**インスタンスを生成する**です。  
  
    > [!NOTE]
    >  選択した PIP の名前の後に "_output" が追加され、さらに .xml 拡張子を付けたファイル名が生成されます。 出力ペインのステートメントにより、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] でインスタンスが作成された場所が示されます。  
  
### <a name="to-modify-the-message-instance-template"></a>メッセージ インスタンス テンプレートを変更するには  
  
1.  [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] エクスプローラーで、目的の XML ファイルが保存されているフォルダーに移動し、そのファイルの名前をダブルクリックして開きます。  
  
2.  他のすべてのテキストの前に、XML のバージョンとエンコードを示す XML ヘッダー タグを追加します。 例:  
  
    ```  
    <?xml version="1.0" encoding="UTF-8" ?>  
    ```  
  
3.  追加した行の後に、DTD を示す DOCTYPE 行を追加します。 たとえば、3A4 発注要求のインスタンスの場合、DOCTYPE 行は次のようになります。  
  
    ```  
    <!DOCTYPE Pip3A4PurchaseOrderRequest SYSTEM "3A4_MS_V02_02_PurchaseOrderRequest.dtd">  
    ```  
  
    > [!NOTE]
    >  各メッセージ インスタンスを処理するには、それぞれ DOCTYPE 行を含める必要があります。  
  
4.  これで、ビジネス ニーズに合わせてこのメッセージ インスタンスをカスタマイズできます。 XML 名前空間または名前空間プレフィックスを使用しないように、XML インスタンスを変更します。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)