---
title: フラット ファイル アセンブラー パイプライン コンポーネントの区切り記号の保持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adc27561-9996-49a9-b715-e313b9148506
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f975f04bb18dca5cc8e311fdb21d7b44caf01d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322132"
---
# <a name="retaining-delimiters-in-the-flat-file-assembler-pipeline-component"></a>フラット ファイル アセンブラー パイプライン コンポーネントの区切り記号の保持
フラット ファイル アセンブラーを使用するカスタム パイプラインを通過するメッセージに不足しているレコードがある場合、そのレコードの区切り記号は可能性があります。 またはによっては、入力ファイル内のレコードが不足しているフラット ファイルの出力が表示されません。  
  
 ように、特定の区切り記号を保持するフラット ファイルを確認する、マップとカスタム スクリプトを使用することができます、メッセージでは、特定の入力レコードが存在しない場合は、「空」のレコードが作成されます。 これを機能させるには、フラット ファイル アセンブラーのドキュメント スキーマの可能性がある空のノードが示すように設定する次のプロパティであることの操作を行う必要があります。  
  
|プロパティ|設定|  
|--------------|-------------|  
|空のデータの区切り記号を保存します。|はい|  
|末尾の区切り記号を非表示します。|いいえ|  
|空のノードの生成 (ルート ノードの設定)|True|  
  
### <a name="to-create-a-map-that-creates-an-empty-record"></a>「空」のレコードを作成するマップを作成するには  
  
1.  新しいマップを BizTalk プロジェクトに追加します。  
  
2.  マップの送信元と送信先スキーマのマップの両方として、フラット ファイル アセンブラーで使用されるドキュメント スキーマを指定します。  
  
3.  対応する先のフィールドを空にならないソース フィールドをマップします。  
  
4.  空にすることをこれらのフィールドに対してカスタム スクリプトを使用して、ソース フィールドが空かを確認し、(Nil) ではなく空の文字列を返します。 次のようなスクリプトを使用します。  
  
    ```  
    public string ValOrEmpty(string val)  
    {  
         return (val.Length > 0) ? val : "";  
    }  
    ```  
  
    > [!NOTE]
    >  マップする可能性がある空のフィールドごとに一意の関数の名前は、スクリプトを作成する必要があります。 たとえば、3 つのフィールドが空になる可能性がある場合は、という名前の関数を必要があります`ValOrEmpty1`、 `ValOrEmpty2`、`ValOrEmpty3`します。  
  
5.  BizTalk Server 管理コンソールを使用して、カスタム パイプラインと送信マップとしてマップを使用するフラット ファイル アセンブラー コンポーネントでの送信ポートを構成します。  
  
## <a name="see-also"></a>参照  
 [送信ポートの送信マップを構成する方法](../core/how-to-configure-outbound-maps-for-a-send-port.md)   
 [フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md)