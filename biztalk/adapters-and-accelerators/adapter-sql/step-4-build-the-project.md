---
title: "手順 4: プロジェクトをビルドします |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d88b1407-ecdd-4dbf-90da-02dc4781568c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f1d6fa03b4a686537ef04f0121c1ae168e525ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-build-the-project"></a>手順 4: プロジェクトをビルドします
![4 のステップ 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **所要時間:** 5 分  
  
 **目標:**この手順では、BizTalk オーケストレーション プロジェクトをコンパイルします。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 3: 応答レコードの挿入と受信する要求メッセージを送信](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)です。  
  
### <a name="to-build-the-biztalk-orchestration-project"></a>BizTalk オーケストレーション プロジェクトをビルドするには  
  
1.  ソリューション エクスプ ローラーで BizTalk プロジェクト名を右クリックし、をクリックして**プロパティ**です。  
  
2.  プロパティ ページ] ダイアログ ボックスのツリー ウィンドウで、[展開**共通プロパティ**をクリックして**アセンブリ**、プロパティ リストをクリックし、**アセンブリ キー ファイル**省略記号**[...]**.  
  
3.  」の説明に従って作成したアセンブリ キー ファイルへのパスを指定して[SQL アダプターを使用して SQL アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)、順にクリック**開く**です。  
  
4.  プロパティ ページ] ダイアログ ボックスのツリー ウィンドウで、[展開**構成プロパティ**をクリックして**展開**、し、次の操作を行います。  
  
    1.  **アプリケーション名**プロパティで、「`SampleApplication`です。  
  
    2.  **再展開**プロパティで、 **True**です。  
  
     **[OK]**をクリックします。  
  
5.  **[ファイル]** メニューの **[すべてを保存]**をクリックします。  
  
6.  ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**ソリューションのビルド**です。  
  
     画面の下部にある出力ウィンドウを読み取る必要があります:**ビルド: 3 の成功または最新、0 失敗、0 スキップします。**  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、BizTalk プロジェクトと 2 つのクラス ライブラリ プロジェクトを含むソリューションをコンパイルします。  
  
## <a name="next-steps"></a>次の手順  
 」の説明に従って、ソリューションの配置[レッスン 5: ソリューションの配置](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)です。  
  
## <a name="see-also"></a>参照  
 [手順 3: レコードを挿入し、応答を受信する要求メッセージを送信します。](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)   
 [レッスン 4: Purchase Order テーブルで挿入操作を実行します。](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)