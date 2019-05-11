---
title: 手順 4:プロジェクトのビルド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d88b1407-ecdd-4dbf-90da-02dc4781568c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6216d96e0d9ce0f8e564fa45bc28c075ce124c8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367696"
---
# <a name="step-4-build-the-project"></a>手順 4:プロジェクトをビルドします
![手順 4 の 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、BizTalk オーケストレーション プロジェクトをコンパイルします。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります[手順 3。レコードを挿入し、応答を受信する要求メッセージの送信](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)します。  
  
### <a name="to-build-the-biztalk-orchestration-project"></a>BizTalk オーケストレーション プロジェクトをビルドするには  
  
1. ソリューション エクスプ ローラーで BizTalk プロジェクト名を右クリックし をクリックし、**プロパティ**します。  
  
2. ツリー ウィンドウで、プロパティ ページ] ダイアログ ボックスで [**共通プロパティ**、 をクリックして**アセンブリ**、プロパティ ボックスの一覧をクリックし、**アセンブリ キー ファイル**省略記号 **[...]**.  
  
3. 」の説明に従って作成したアセンブリ キー ファイルへのパスを指定[SQL アダプターを使用して SQL アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)、 をクリックし、**オープン**します。  
  
4. ツリー ウィンドウで、プロパティ ページ ダイアログ ボックスで **構成プロパティ**、 をクリックして**展開**、し、次の操作を行います。  
  
   1. **アプリケーション名**プロパティに「`SampleApplication`します。  
  
   2. **再デプロイ**プロパティで、 **True**します。  
  
      **[OK]** をクリックします。  
  
5. **[ファイル]** メニューの **[すべてを保存]** をクリックします。  
  
6. ソリューション エクスプ ローラーでソリューション名を右クリックし をクリックし、**ソリューションのビルド**します。  
  
    画面の下部にある出力ウィンドウは次のようになります。**ビルド:3 つ成功または最新、0 失敗、0 スキップされます。**  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順では、BizTalk プロジェクトと 2 つのクラス ライブラリ プロジェクトを含むソリューションをコンパイルします。  
  
## <a name="next-steps"></a>次の手順  
 」の説明に従って、ソリューションの配置[レッスン 5。ソリューションの配置](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)します。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:レコードを挿入し、応答を受信する要求メッセージを送信します。](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)   
 [レッスン 4:注文テーブルに対して挿入操作を実行する](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)