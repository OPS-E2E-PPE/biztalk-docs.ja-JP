---
title: "Web ポートを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web ports, creating
- creating, Web ports
ms.assetid: da94d98e-10ca-437a-ba34-7aa6efc68f3d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42e9853755788aa29d3ca7506829dcd6bdfed53d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-web-port"></a>Web ポートを追加する方法
Web ポートの追加には、オーケストレーション デザイナのポート画面を使用します。 他の構成済みのポートと異なり、Web ポートでは要求(一方向) と要求 - 応答 (双方向) 操作を混在させることができます。 Web ポート内の各操作は、1 つの Web メソッドを表します。 Web メソッドが含まれている場合*入力*と*出力*パラメーター、BizTalk は、要求/応答操作を作成します。 Web サービスにのみ含まれている場合、*入力*パラメーター、BizTalk はのみ一方向の操作を作成します。  
  
### <a name="to-add-a-web-port"></a>Web ポートを追加するには  
  
1.  オーケストレーション デザイナーで、オーケストレーションを開き、ポート画面を右クリックし **新しい構成済みポート**です。  
  
2.  **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]**をクリックします。  
  
3.  **ポートのプロパティ**] ページの [、**名前**テキスト ボックス、ポートの名前を入力し、をクリックして**次**です。  
  
4.  **ポートの種類を選択して** ページで選択**既存のポートの種類を使用して**です。  
  
5.  **使用可能なポートの種類**ボックスで、展開、 **Web ポートの種類**ノードを選択、Web ポートの種類、追加された Web サービスに対応して、をクリックして**次**です。  
  
     次の図に示しています、**ポートの種類を選択して** ダイアログ ボックス。  
  
     ![](../core/media/ebiz-prog-ws-addwebport.gif "ebiz_prog_ws_addwebport")  
  
6.  **ポートのバインド**] ページの [、**ポートのバインド**ドロップダウン ボックスで、**今指定**です。 BizTalk によって、URI、トランスポート、受信パイプライン、および送信パイプラインについて、参照先の Web サービスの値が自動的に設定されます。 BizTalk プロジェクトを展開すると、BizTalk はこれらの値を使用して送信ポートを作成します。  
  
    > [!IMPORTANT]
    >  送信ポートの既定の認証方法には、匿名アクセスが使用されます。 Web サービスが別の認証方法や暗号化方法を要求する場合は、構成を変更し、Web サービスの実行に適切なユーザー資格情報や Secure Sockets Layer (SSL) を適用します。 詳細については、次を参照してください。 [SOAP 送信アダプタ](../core/soap-send-adapter.md)と[サンプル TMA: HTTP アダプタと SOAP アダプタ](../core/sample-tma-http-and-soap-adapters.md)です。  
  
7.  をクリックして**[次へ]**、し**完了**ウィザードを完了します。  
  
## <a name="see-also"></a>参照  
 [ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md)   
 [Web ポートの作成](../core/creating-web-ports.md)