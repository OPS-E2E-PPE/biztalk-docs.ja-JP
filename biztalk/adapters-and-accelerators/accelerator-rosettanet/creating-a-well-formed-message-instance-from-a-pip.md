---
title: PIP からの整形式メッセージ インスタンスの作成 |Microsoft Docs
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
ms.openlocfilehash: dc0dc9610b171ffa2049c5a4951d3846451aa2db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284688"
---
# <a name="creating-a-well-formed-message-instance-from-a-pip"></a>PIP からの整形式メッセージ インスタンスの作成
このトピックでは、整形式メッセージ インスタンスを生成する方法について説明します。 メッセージ インスタンス テンプレートは、パートナー インターフェイス プロセス (PIP) から生成できます。 これを行うには、変更する必要が、そのテンプレートには、整形式で、データを追加する前にするためです。  
  
### <a name="to-generate-a-message-instance-template-from-the-pip"></a>PIP からメッセージ インスタンス テンプレートを生成するには  
  
1. 開始**Microsoft Visual Studio 2012**します。  
  
2. **ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト**。  
  
3. 検索\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanetsdk \schemas に移動、クリックして**RNPIPs.btproj**、クリックして**オープン**します。  
  
4. ソリューション エクスプ ローラーで、 **Rnpip**インスタンスを作成する PIP を右クリックします。  
  
5. クリックして**インスタンスの生成**します。  
  
   > [!NOTE]
   >  これには、"_output"ファイル名に付加され、.xml 拡張子後、PIP という名前のファイルが生成されます。 [出力] ウィンドウ内のステートメントは、位置を示します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]インスタンスを生成します。  
  
### <a name="to-modify-the-message-instance-template"></a>メッセージ インスタンス テンプレートを変更するには  
  
1. [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーでは、XML ファイルを保持しているフォルダーに移動し、フォルダーを開く、ファイル名をダブルクリックします。  
  
2. XML とエンコーディングのバージョンを示すその他のすべてのテキストの前に、XML ヘッダー タグを追加します。 以下に例を示します。  
  
   ```  
   <?xml version="1.0" encoding="UTF-8" ?>  
   ```  
  
3. 追加した行の後に、DTD を示す DOCTYPE 行を追加します。 たとえば、3A4 発注書要求のインスタンスでは、行とおりのようになります  
  
   ```  
   <!DOCTYPE Pip3A4PurchaseOrderRequest SYSTEM "3A4_MS_V02_02_PurchaseOrderRequest.dtd">  
   ```  
  
   > [!NOTE]
   >  各メッセージ インスタンスには、処理の DOCTYPE 行を含める必要があります。  
  
4. これで、ビジネス ニーズに合わせてこのメッセージ インスタンスをカスタマイズできます。 XML インスタンスを変更するは、XML 名前空間または名前空間プレフィックスを使用しないようにします。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)