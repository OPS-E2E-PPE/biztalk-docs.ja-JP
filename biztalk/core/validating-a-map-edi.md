---
title: "マップ (EDI) の検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: caf58ecf-ed10-4c13-8d7d-e007b9158b0e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 028a152be285bb79f3cd0899b2143e99ef2b6042
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="validating-a-map-edi"></a>マップの検証 (EDI)
マップは、デザイン時に検証できます。 XML ツール拡張機能を使用するためには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]環境。 検証を行うと、マップの基になる XSLT を含むファイルと、拡張オブジェクトを含むファイルが生成されます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-validate-a-map"></a>マップを検証するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトを開きます。 ソリューション エクスプローラーで、検証するマップと、その入力および出力のメッセージ スキーマをプロジェクトに追加します。  
  
    > [!NOTE]
    >  メッセージ スキーマは [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder フォルダーの下の該当するサブフォルダーにあります。 スキーマ ファイルのインストールの詳細については、次を参照してください。 [EDI スキーマ ファイルをインストールする方法](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550)です。  
  
    > [!NOTE]
    >  マップを検証するためにプロジェクトをビルドする必要はありません。  
  
2.  ソリューション エクスプ ローラーでマップを右クリックし、をクリックして**マップの検証**です。  
  
3.  操作が成功したことを示すメッセージが [出力] ウィンドウに表示されていることを確認します。  
  
4.  すべての警告に注意してくださいを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でをポストしましたが、**出力**ウィンドウです。  
  
5.  **出力**ウィンドウ、出力された XSLT のパスと名前に注意してください。 この XSL ファイルにはマップ ファイルと同じ名前が設定されます。ただし、拡張子は XSL です。 Ctrl キーを押しながらリンクをクリックすると、BizTalk エディターに XSL ファイルが表示されます。  
  
6.  **出力**ウィンドウで、拡張オブジェクト XML のパスと名前に注意してください。 Ctrl キーを押しながらリンクをクリックすると、BizTalk エディターに XSL ファイルが表示されます。  
  
## <a name="see-also"></a>参照  
 [デザイン時 XML ツールを使用します。](../core/using-design-time-xml-tools.md)