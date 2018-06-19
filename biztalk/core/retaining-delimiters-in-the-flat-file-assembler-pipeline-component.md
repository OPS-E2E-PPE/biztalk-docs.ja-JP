---
title: フラット ファイル アセンブラー パイプライン コンポーネントの区切り記号の保持 |Microsoft ドキュメント
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
ms.openlocfilehash: d9d10879adfbe0ca0c68376faa48d9976fc19599
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268786"
---
# <a name="retaining-delimiters-in-the-flat-file-assembler-pipeline-component"></a>フラット ファイル アセンブラー パイプライン コンポーネントでの区切り記号の保持
フラット ファイル アセンブラーを使用するカスタム パイプラインを通るメッセージに、レコードが不足している場合、フラット ファイルの出力にレコードの区切り記号が表示されるかどうかは、入力ファイルのどこでレコードが不足しているかによって決まります。  
  
 フラット ファイルに特定の区切り記号が保持されるようにするには、マップとカスタム スクリプトを使用できます。これにより、特定の入力レコードがメッセージ内に存在しないときに "空の" レコードが確実に作成されます。 これが機能するためには、フラット ファイル アセンブラーのドキュメント スキーマで空になる可能性があるノードに、次のようにプロパティを設定する必要があります。  
  
|プロパティ|設定|  
|--------------|-------------|  
|空のデータの区切り記号を保存します。|はい|  
|末尾の区切り記号の非表示|不可|  
|空のノードを生成 (ルート ノードに設定)|True|  
  
### <a name="to-create-a-map-that-creates-an-empty-record"></a>"空の" レコードを作成するマップを作成するには  
  
1.  BizTalk プロジェクトに新しいマップを追加します。  
  
2.  フラット ファイル アセンブラーによって使用されるドキュメント スキーマを、マップの送信元スキーマと送信先スキーマの両方に指定します。  
  
3.  空にならないソース フィールドを、対応するマップ先フィールドにマップします。  
  
4.  空になる可能性があるフィールドに対しては、ソース フィールドが空であるかどうかを確認して (Nil の代わりに) 空の文字列を返すカスタム スクリプトを使用します。 次のようなスクリプトを使用します。  
  
    ```  
    public string ValOrEmpty(string val)  
    {  
         return (val.Length > 0) ? val : "";  
    }  
    ```  
  
    > [!NOTE]
    >  空になる可能性があるマップ対象フィールドごとに、一意の関数名を持つスクリプトを作成する必要があります。 たとえば、空になる可能性があるフィールドが 3 つある場合、`ValOrEmpty1`、`ValOrEmpty2`、および `ValOrEmpty3` という名前の関数を使用できます。  
  
5.  カスタム パイプラインと送信マップとしてマップを使用するフラット ファイル アセンブラー コンポーネントでの送信ポートを構成する BizTalk Server 管理コンソールを使用します。  
  
## <a name="see-also"></a>参照  
 [送信ポートの送信マップを構成する方法](../core/how-to-configure-outbound-maps-for-a-send-port.md)   
 [フラット ファイル アセンブラー パイプライン コンポーネント](../core/flat-file-assembler-pipeline-component.md)