---
title: マップなしのマップを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 520ec44f-5aca-4271-8835-b8e784214061
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81be2591c1d8f20f5b8dd01cf01c03e8daed9c9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248794"
---
# <a name="how-to-create-a-map-without-maps"></a>マップを使用しないでマップを作成する方法
インスタンス メッセージを変換するための XSLT コードが既に手元にある場合は、マップを作成する代わりに、XSLT コードを使って直接データを変換できます。  
  
 空のマップを作成および設定は、XSLT コードを使用してその**カスタム XSLT パス**グリッド プロパティです。 XSLT コードでは、外部 .NET アセンブリを使用する場合は、カスタム拡張 XML ファイルを作成する必要があります。 カスタム拡張 XML ファイルの構造については、次を参照してください。、**カスタム拡張 XML (グリッド プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="use-custom-xslt-code-in-place-of-a-map"></a>マップの代わりにカスタムの XSLT コードを使用します。  
  
1.  空の BizTalk マップをプロジェクトに作成し、送信元スキーマおよび送信先スキーマを設定します。  
  
     マップを作成して、スキーマの設定については、次を参照してください。[マップの作成](../core/creating-maps.md)です。  
  
2.  グリッド ビューで、マッパー グリッドをクリックします。  
  
     プロパティ ウィンドウの表示、**グリッド**プロパティです。  
  
3.  [プロパティ] ウィンドウで選択**カスタム XSLT パス**、省略記号ボタンをクリックし、(**.**) ボタンをクリックします。  
  
4.  **開く** ダイアログ ボックスで、ファイルに移動し、をクリックして**開く**です。  
  
     **カスタム XSLT パス**プロパティを設定します。  
  
> [!NOTE]
>  BizTalk マッパーは XSLT 1.0 のみをサポートします。 XSLT 2.0 の使用は、BizTalk マッパーではサポートされていません。  
  
## <a name="see-also"></a>参照  
 [マップの概要](../core/about-maps.md)   
 [スクリプトを使用してインライン XSLT および XSLT 呼び出しテンプレート](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [カスタム xslt は上書き](../core/custom-xslt.md)   