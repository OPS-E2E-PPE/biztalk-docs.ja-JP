---
title: "WCF LOB Adapter SDK を使用してバインド プロパティとしてアダプターの設定を公開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59728113-917e-4bca-8e1a-609cd6558944
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c72ba43378829c71bfb3379bb70ea274de652c9b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用してバインド プロパティとしてアダプターの設定を公開します。
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]接続プール、メタデータのキャッシュ、およびその他のアダプターの動作を構成するためのさまざまなクラスで定義されたプロパティを使用します。 このトピックは、アダプターのコンシューマーが構成ファイルで設定できるように、バインディングのプロパティとしてこれらのプロパティを表面化する方法について説明します。  
  
### <a name="to-surface-an-adapter-setting-as-an-adapter-binding-property"></a>アダプターのバインド プロパティとしてアダプターの設定を表示するには  
  
1.  Visual Studio を起動し、**ファイル** メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
2.  選択、 **WCF LOB アダプター**テンプレート、その他のアダプター プロジェクトの情報を指定します。  
  
3.  ステップ実行、[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]です。 取得するときに、**アダプター プロパティ** ページで、提供することで公開するバインディングのプロパティを追加、**プロパティ名**、**データ型**、および**既定値**、クリックして**追加**新しいアダプター プロパティを追加します。  
  
4.  完了、[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]です。 プロジェクトには、ウィザードによって提供される新しいファイルを追加する必要があります。  
  
5.  ソリューション エクスプ ローラーで、Visual Studio では、アダプターから派生したクラスを開きます。 たとえば、アダプター プロジェクトの名前が"SampleAdapter"の場合は、アダプターの派生クラスを"SampleAdapter.cs"で確認できます。  
  
6.  取得し、アダプターの設定から設定するプロパティのプライベート変数を削除します。 プライベート変数がによって生成された、[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]です。  
  
7.  読み取り/書き込みから/にアダプターの設定値を取得または設定メソッドを更新します。 次の例では、アダプターのプロパティを使用して、パフォーマンス カウンターの有効化を許可します。  
  
    ```  
    [System.Configuration.ConfigurationProperty("enablePerfCounters", DefaultValue = false)]  
    public bool EnablePerfCounters  
    {  
        get { return environmentSettings.PerformanceCounters.Enabled;    }  
        set { environmentSettings.PerformanceCounters.Enabled = value; }  
    }  
    ```  
  
8.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: エコー アダプターを開発する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)[開発アクティビティ](../../esb-toolkit/development-activities.md)