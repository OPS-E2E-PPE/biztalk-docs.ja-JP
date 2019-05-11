---
title: XSD ベース PIP のインポート |Microsoft Docs
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
ms.openlocfilehash: b8d1a0d6b4fe835a38dc5eaf19a328b14e0d288f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283667"
---
# <a name="importing-an-xsd-based-pip"></a>XSD ベース PIP のインポート
ほとんどの PIP を RosettaNet.org によって提供されるは DTD ベース、新しい PIP は XSD ベースです。 次の手順では、XSD ベース PIP をインポートする方法について説明します。  
  
### <a name="to-import-an-xsd-based-pip"></a>XSD ベース PIP をインポートするには  
  
1.  XSD ベース PIP の .zip ファイルをダウンロードで RosettaNet.org からダウンロードした[ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=33859)または CIDX.org から[ http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361)します。 .Zip ファイルからファイルを抽出します。 必要なファイルは、XML フォルダーのサブフォルダーになります。  
  
2.  Visual Studio を開きます。 新しい BizTalk プロジェクトを作成します。  
  
3.  Windows エクスプ ローラーを開き、手順 1. で解凍した XML フォルダーに移動します。 XML フォルダーの下の最初のフォルダーを選択、Visual Studio で、ソリューション エクスプ ローラーにドラッグし、プロジェクトにドロップします。 プロジェクトと同じフォルダー構造を作成する、XML フォルダー内のサブフォルダーのごとに繰り返します。  
  
    > [!NOTE]
    >  PIP7c7 PIP のこれらのフォルダーが、ドメイン、インターチェンジ、システム、および Universal フォルダーが含まれます。 この pip では、プロジェクトは、ドメイン、インターチェンジ、システム、および Universal フォルダーとその内容を含める必要があります。  
  
4.  システム フォルダーに .xsd ファイルがある場合は、ソリューション エクスプ ローラーで選択してプロパティ ページには、文字列が含まれていないように表示する名前空間を変更"。システム"。 たとえば、PIP7c7 pip で"pip7c7._system"に名前空間を変更します。 システム フォルダー内の各 .xsd ファイルに対して繰り返します。 名前空間を変更しない場合または、次のようなエラーが表示されます。  
  
    ```  
    The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'PIP7C7.System'.  
    ```  
  
5.  いることを確認するすべての .xsd ファイルを確認、\<スキーマ\>TypeName およびルート ノード TypeName が同一でないです。 たとえば、PIP7C7 PIP の Universal フォルダで PartnerIdentification.xsd が 'partneridentification 'という TypeName 両方の\<スキーマ\>(PartnerIdentification.xsd を選択するとソリューション エクスプ ローラーで) とも、PartnerIdentification ルート ノードです。 これを修正するには、ソリューション エクスプ ローラーで PartnerIdentification.xsd を選択し、プロパティ ページで変更 TypeName プロパティ PartnerIdentification ルート ノードとして同じ型名が含まれていないようにします。 たとえば、TypeName を"_partneridentification"を変更します。 この手順を実行しない場合、プロジェクトをビルドするときに、次のエラーを受け取ります。  
  
    ```  
    Node "<Schema>" - This schema file has a TypeName that collides with the RootNode TypeName of one of its root Nodes. Make sure that they are different.  
    ```  
  
    > [!NOTE]
    >  エラー一覧 に ファイル 列では、この問題があるファイルを示します。  
  
6.  ビルドし、プロジェクトを配置します。