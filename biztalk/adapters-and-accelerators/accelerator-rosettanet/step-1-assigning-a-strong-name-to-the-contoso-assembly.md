---
title: "手順 1: Contoso アセンブリへの厳密な名前の割り当て |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, assigning strong-names
- strong-named assemblies
ms.assetid: c8ec4593-5a4d-47ab-8799-7b2cd3d15ffc
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7124561b9f842a7cc980c7a54230cd122ae32856
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-assigning-a-strong-name-to-the-contoso-assembly"></a>手順 1: Contoso アセンブリへの厳密な名前の割り当てください。
ここでは、BizTalk アセンブリの厳密な名前を作成して割り当てます。 厳密な名前により、デジタル署名と一意のキーのペアを割り当てることで、アセンブリの一意性を保証します。 また、アセンブリの内容が最後にビルドされてから変更されていないことを保証するための整合性チェックも行えます。  
  
### <a name="to-create-a-strong-name-assembly-key-file"></a>厳密な名前のアセンブリー キー ファイルを作成するには  
  
1.  開始**Visual Studio 2012 コマンド プロンプト**です。  
  
2.  コマンド プロンプトで、Contoso ソリューションの場所に移動します。  
  
    > [!NOTE]
    >  既定では、Contoso ソリューションの場所は*\<ドライブ >*: \Documents and 設定\\*\<ユーザー名 >*\My Documents\Visual Studio \<バージョン > \Projects です。  
  
3.  コマンド プロンプトで次のように入力します。 **sn-k FabConPriceAvail.snk**、キーを押します**Enter**です。  
  
4.  コマンド プロンプトで次のように入力します。**終了**、キーを押します**Enter**です。  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>アセンブリに厳密な名前を割り当てるには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **ContosoPriceAndAvailability**プロジェクトをクリックして**プロパティ**です。  
  
2.  プロパティ ページで、をクリックして**署名**左側のウィンドウでします。  
  
3.  右側のペインで選択**アセンブリに署名**です。  
  
4.  をクリックして**参照**厳密な名前キー ファイル フィールドの選択 でします。  
  
5.  プロジェクト フォルダで、選択、 **FabConPriceAvail.snk**クリックして、前に作成したファイルに**開く**です。  
  
6.  をクリックして**OK**変更を保存します。  
  
7.  ソリューション エクスプ ローラーで右クリックし、 **ContosoPriceAndAvailability**プロジェクトをクリックして**ビルド**です。 ビルドが完了すると、もう一度、プロジェクトを右クリックし、クリックして**展開**です。  
  
## <a name="see-also"></a>参照  
 [手順 2: Contoso 3 a 2 Price and Availability クエリ/応答シナリオ用のポートの作成](step-2-create-ports-for-contoso-3a2-price-and-availability-query.md)