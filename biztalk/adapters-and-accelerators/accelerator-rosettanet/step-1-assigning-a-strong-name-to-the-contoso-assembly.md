---
title: 手順 1:Contoso アセンブリへの厳密な名前の割り当て |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, assigning strong-names
- strong-named assemblies
ms.assetid: c8ec4593-5a4d-47ab-8799-7b2cd3d15ffc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17ce82403581101a2cc88749a40cbdb786e54a97
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281704"
---
# <a name="step-1-assigning-a-strong-name-to-the-contoso-assembly"></a>手順 1:Contoso アセンブリへの厳密な名前の割り当てください。
この手順では、作成し、BizTalk アセンブリの厳密な名前を割り当てます。 厳密な名前では、デジタル署名と一意キーのペアを割り当てることで、アセンブリの一意性を保証します。 さらに、厳密な名前は、アセンブリの内容が前回のビルド以降に変更していないことを保証するために、整合性チェックを提供します。  
  
### <a name="to-create-a-strong-name-assembly-key-file"></a>厳密な名前のアセンブリー キー ファイルを作成するには  
  
1.  開始**Visual Studio 2012 のコマンド プロンプト**します。  
  
2.  コマンド プロンプトで、Contoso ソリューションの場所に移動します。  
  
    > [!NOTE]
    >  既定では、Contoso ソリューションの場所は*\<ドライブ\>*: \Documents and Settings\\*\<ユーザー名\>* \MyDocuments \visual Studio\<バージョン\>\Projects です。  
  
3.  コマンド プロンプトで「 **sn-k FabConPriceAvail.snk**、キーを押しますと **」と入力**します。  
  
4.  コマンド プロンプトで「**終了**、押します **」と入力**します。  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>アセンブリに厳密な名前を割り当てる  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **ContosoPriceAndAvailability**プロジェクトをクリックして**プロパティ**します。  
  
2.  [プロパティ ページ] でクリックして**署名**左側のウィンドウでします。  
  
3.  右側のウィンドウで次のように選択します。**アセンブリに署名**します。  
  
4.  クリックして**参照**厳密な名前キー ファイルのフィールドの選択 でします。  
  
5.  プロジェクト フォルダーを見つけ、選択、 **FabConPriceAvail.snk**クリックして、先ほど作成したファイルに**オープン**します。  
  
6.  **[OK]** をクリックして変更を保存します。  
  
7.  ソリューション エクスプ ローラーで右クリックし、 **[contosopriceandavailability]** プロジェクトをクリックして**ビルド**します。 ビルドが完了すると、もう一度、プロジェクトを右クリックし、クリックして**デプロイ**します。  
  
## <a name="see-also"></a>参照  
 [手順 2:Contoso 3 a 2 Price and Availability クエリ/応答シナリオ用のポートの作成](step-2-create-ports-for-contoso-3a2-price-and-availability-query.md)