---
title: Web ポートを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web ports, creating
- creating, Web ports
ms.assetid: da94d98e-10ca-437a-ba34-7aa6efc68f3d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a67cfd33aeace3b6cfde9f1e0a7e87831d7972ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387337"
---
# <a name="how-to-add-a-web-port"></a>Web ポートを追加する方法
オーケストレーション デザイナのポート画面には、Web ポートを追加します。 他の構成済みのポートとは異なりは、Web ポートは、(一方向) の要求と要求/応答 (双方向) 操作の組み合わせをサポートします。 Web ポート内の各操作では、Web メソッドを表します。 Web メソッドが含まれている場合*入力*と*出力*パラメーターでは、BizTalk は要求/応答操作を作成します。 Web サービスにのみ含まれている場合、*入力*パラメーターでは、BizTalk はのみ一方向の操作を作成します。  
  
### <a name="to-add-a-web-port"></a>Web ポートを追加するには  
  
1.  オーケストレーション デザイナのオーケストレーションを開き、ポート画面を右クリックし **新しい構成済みポート**します。  
  
2.  **[ポート構成ウィザードへようこそ]** ページで、 **[次へ]** をクリックします。  
  
3.  **ポートのプロパティ**] ページの [、**名前**テキスト ボックスに、ポートの名前を入力し、順にクリックします**次**します。  
  
4.  **ポートの種類を選択します。** ] ページで [**既存のポートの種類を使用して、**。  
  
5.  **使用可能なポートの種類**ボックスで、展開、 **Web ポートの種類**ノードと選択、Web ポートの追加の Web サービスに対応する種類をクリックして**次**します。  
  
     次に示します、**ポートの種類を選択します。**  ダイアログ ボックス。  
  
     ![](../core/media/ebiz-prog-ws-addwebport.gif "ebiz_prog_ws_addwebport")  
  
6.  **ポートのバインド**ページで、**ポートのバインド**ドロップダウン ボックスで、**今指定する**します。 BizTalk が自動的に、URI、トランスポートに参照する Web サービスから値を格納し、受信および送信パイプラインです。 BizTalk では、これらの値を使用して、BizTalk プロジェクトを展開するときに、送信ポートを作成します。  
  
    > [!IMPORTANT]
    >  送信ポートの既定の認証方法は、匿名アクセスです。 Web サービスには、さまざまな認証または暗号化の方法が必要とする場合は、適切なユーザーの資格情報または Secure Sockets Layer (SSL) Web サービスの実行に提供する構成を変更する必要があります。 詳細については、次を参照してください[SOAP 送信アダプタ](../core/soap-send-adapter.md)と[サンプル TMA:。HTTP アダプターと SOAP アダプター](../core/sample-tma-http-and-soap-adapters.md)します。  
  
7.  をクリックして **[次へ]**、し**完了**ウィザードを完了します。  
  
## <a name="see-also"></a>参照  
 [ポート構成ウィザードを実行する方法](../core/how-to-run-the-port-configuration-wizard.md)   
 [Web ポートの作成](../core/creating-web-ports.md)