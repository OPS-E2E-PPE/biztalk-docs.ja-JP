---
title: XSD ベース PIP のインポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, importing
- XSD-based PIPs
- PIPs, XSD-based PIPs
ms.assetid: d12441d4-79bf-4c24-9360-4b78c1da0d34
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d8865d7a75bdb06895b963b8269ed457cd5804f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961656"
---
# <a name="importing-an-xsd-based-pip"></a>XSD ベース PIP のインポート
RosettaNet.org によって提供されるほとんどの PIP は DTD ベースですが、新しい PIP は XSD ベースです。 次の手順では、XSD ベースの PIP をインポートする方法を示します。  
  
### <a name="to-import-an-xsd-based-pip"></a>XSD ベース PIP のインポートするには  
  
1.  XSD ベース PIP の .zip ファイルに RosettaNet.org からダウンロード[http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859)または CIDX.org から[http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361)です。 .zip ファイルからファイルを解凍します。 必要なファイルは、XML フォルダーのサブフォルダー内にあります。  
  
2.  Visual Studio を開きます。 新しい BizTalk プロジェクトを作成します。  
  
3.  Windows エクスプローラーを開き、手順 1. で解凍した XML フォルダーに移動します。 XML フォルダー内の 1 番目のフォルダーを選択し、それを Visual Studio のソリューション エクスプローラーまでドラッグし、作成したプロジェクトにドロップします。 XML フォルダー内のすべてのサブフォルダーに対してこの手順を繰り返し、作成したプロジェクトに同じフォルダー構造を作成します。  
  
    > [!NOTE]
    >  PIP7c7 PIP では、これらのフォルダーには Domain、Interchange、System、および Universal フォルダーが含まれています。 この PIP では、新しく作成したプロジェクトに Domain、Interchange、System、および Universal フォルダーがそのコンテンツと共に作成されている必要があります。  
  
4.  System フォルダーに .xsd ファイルがある場合、ソリューション エクスプローラーでそのファイルを選択し、プロパティ ページに一覧表示されている名前空間を変更します。この操作によって、ファイルに ".System" という文字列は含まれなくなります。 たとえば、PIP7c7 PIP で、名前空間を "PIP7c7._System" に変更します。 System フォルダの各 .xsd ファイルでこの手順を繰り返します。 名前空間を変更しないと、次のようなエラーが発生します。  
  
    ```  
    The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'PIP7C7.System'.  
    ```  
  
5.  いることを確認するすべての .xsd ファイルを確認、\<スキーマ\>TypeName およびルート ノード TypeName が同一でありません。 たとえば、PIP7C7 PIP の Universal フォルダで PartnerIdentification.xsd が 'partneridentification 'という TypeName の両方、\<スキーマ\>(PartnerIdentification.xsd を選択するとソリューション エクスプ ローラーで) とも、PartnerIdentification ルート ノードです。 この問題を修正するには、ソリューション エクスプローラーで PartnerIdentification.xsd を選択し、プロパティ ページ内で  TypeName プロパティを変更します。この操作によって、TypeName が PartnerIdentification ルート ノードと同一になることを回避できます。 たとえば、TypeName を "_PartnerIdentification" に変更します。 この手順を実行しないと、プロジェクトのビルドの実行時に次のエラーが発生します。  
  
    ```  
    Node "<Schema>" - This schema file has a TypeName that collides with the RootNode TypeName of one of its root Nodes. Make sure that they are different.  
    ```  
  
    > [!NOTE]
    >  エラー一覧の [ファイル] 列には、どのファイルにこの問題が存在しているかが表示されます。  
  
6.  プロジェクトをビルドし、展開します。