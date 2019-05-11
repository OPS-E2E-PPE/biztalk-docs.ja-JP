---
title: WCF LOB Adapter SDK を使用してバインドのプロパティとしてアダプターの設定を公開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59728113-917e-4bca-8e1a-609cd6558944
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bae73accfb6e65624f672ce1674b9e0429b6f3da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363636"
---
# <a name="expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用してバインドのプロパティとしてアダプターの設定を公開します。
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]接続プール、メタデータのキャッシュ、およびその他のアダプターの動作を構成するためのさまざまなクラスで定義されたプロパティを使用します。 このトピックでは、アダプターのコンシューマーが、構成ファイルで設定できるようにバインドのプロパティとしてこれらのプロパティを表示する方法について説明します。  
  
### <a name="to-surface-an-adapter-setting-as-an-adapter-binding-property"></a>アダプターのバインド プロパティとしてアダプターの設定を表示するには  
  
1. Visual Studio を起動し、**ファイル**メニューで、**新規**、 をクリックし、**プロジェクト**します。  
  
2. 選択、 **WCF LOB アダプター**テンプレート、その他のアダプター プロジェクト情報を指定します。  
  
3. ステップ実行、[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]します。 取得するときに、**アダプター プロパティ**ページで、追加のバインドのプロパティを提供することで公開する、**プロパティ名**、**データ型**、および**既定値**、 をクリックし、**追加**新しいアダプターのプロパティを追加します。  
  
4. 完了、[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]します。 プロジェクトには、ウィザードによって提供される新しいファイルを含める必要があります。  
  
5. ソリューション エクスプ ローラーで、Visual Studio では、アダプターから派生したクラスを開きます。 たとえば、アダプター プロジェクトの名前が"SampleAdapter"の場合は、派生アダプター クラスを"SampleAdapter.cs"で確認できます。  
  
6. アダプターの設定から設定を取得するプロパティのプライベート変数を削除します。 によって生成された秘密の変数、[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]します。  
  
7. アダプターの設定を値の読み取り/書き込みを get/set メソッドを更新します。 次の例は、アダプターのプロパティを使用して、パフォーマンス カウンターの有効化を許可します。  
  
   ```  
   [System.Configuration.ConfigurationProperty("enablePerfCounters", DefaultValue = false)]  
   public bool EnablePerfCounters  
   {  
       get { return environmentSettings.PerformanceCounters.Enabled;    }  
       set { environmentSettings.PerformanceCounters.Enabled = value; }  
   }  
   ```  
  
8. Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1:エコー アダプターを開発](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)[開発アクティビティ](../../esb-toolkit/development-activities.md)