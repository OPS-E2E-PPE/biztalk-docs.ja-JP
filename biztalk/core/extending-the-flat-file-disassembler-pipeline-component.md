---
title: フラット ファイル逆アセンブラー パイプライン コンポーネントの拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, code sample
- pipeline components [custom], flat file documents
- pipeline components [custom], disassembling
ms.assetid: 4bcc746a-696a-4e5c-be01-f8409fce21fa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f19184087c18b901944382c4a421c14c1911e4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388222"
---
# <a name="extending-the-flat-file-disassembler-pipeline-component"></a><span data-ttu-id="a0654-102">フラット ファイル逆アセンブラー パイプライン コンポーネントの拡張</span><span class="sxs-lookup"><span data-stu-id="a0654-102">Extending the Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="a0654-103">次の例は、utf-7 でエンコードされたフラット ファイル ドキュメントを解析するカスタム逆アセンブラーを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a0654-103">The following sample illustrates how to create a custom disassembler to parse flat file documents that are UTF-7 encoded.</span></span> <span data-ttu-id="a0654-104">コンポーネントが継承、utf-7 ドキュメントを処理する、 **FFDasmComp**クラスとし、上書き、 **GetDataReader**メソッド。</span><span class="sxs-lookup"><span data-stu-id="a0654-104">To process UTF-7 documents, the component inherits from the **FFDasmComp** class and then overrides its **GetDataReader** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0654-105">例</span><span class="sxs-lookup"><span data-stu-id="a0654-105">Example</span></span>  
  
```  
using System;  
using System.Text;  
using System.IO;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.Component.Interop;  
using Microsoft.BizTalk.ParsingEngine;  
using Microsoft.BizTalk.Component;  
using System.Runtime.InteropServices;  
  
namespace Microsoft.BizTalk.Test  
{  
   /// <summary>  
   /// Implements FF disassembler which always uses UTF-7 encoding.  
   /// </summary>  
   [ComponentCategory(CategoryTypes.CATID_PipelineComponent)]  
   [ComponentCategory(CategoryTypes.CATID_DisassemblingParser)]  
   [ComponentCategory(CategoryTypes.CATID_Streamer)]  
   [Guid("A6E5F54F-7902-4e1a-84D8-5C7584F0ECF2")]  
   public class Utf7FFDasm :   
      FFDasmComp,  
      IBaseComponent  
   {  
      /// <summary>  
      /// Initializes a Utf7FFAsmDasm instance.  
      /// </summary>  
      public Utf7FFDasm()  
      {  
      }  
  
      /// <summary>  
      /// Name property  
      /// </summary>  
      public new string Name   
      {  
         get   
         {  
            return "UTF-7 FlatFile Disassembler";  
         }  
      }  
  
      /// <summary>  
      /// Version property  
      /// </summary>  
      public new string Version   
      {  
         get   
         {  
            return "1.0";  
         }  
      }  
  
      /// <summary>  
      /// Description property  
      /// </summary>  
      public new string Description   
      {  
         get   
         {  
            return "UTF-7 FlatFile Disassembler";  
         }  
      }  
  
      /// <summary>  
      /// Gets a data reader instance  
      /// </summary>  
      /// <param name="dataStream">Data stream</param>  
      /// <param name="dataEncoding">Data encoding</param>  
      /// <param name="detectEncodingFromByteOrderMarks">Detect encoding from a byte order mark</param>  
      /// <returns>IDataReader instance</returns>  
      protected override IDataReader GetDataReader(Stream dataStream, Encoding dataEncoding, bool detectEncodingFromByteOrderMarks)  
      {  
         // Delegate call to the base implementation passing fixed UTF-7 encoding  
            return base.GetDataReader(dataStream, Encoding.UTF7, false);  
      }  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="a0654-106">例</span><span class="sxs-lookup"><span data-stu-id="a0654-106">Example</span></span>  
 <span data-ttu-id="a0654-107">次の例では、フラット ファイル インターチェンジのトランザクション処理のカスタム逆アセンブラーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a0654-107">The following example illustrates how to create a custom disassembler for transactional processing of flat file interchanges.</span></span> <span data-ttu-id="a0654-108">入力されたインターチェンジ全体が完全に処理されるまで、逆アセンブルしたドキュメントを生成しないことで、標準のフラット ファイル逆アセンブラーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="a0654-108">It differs from the standard Flat File Disassembler in that it does not produce any disassembled documents until the entire input interchange is completely processed.</span></span> <span data-ttu-id="a0654-109">このコンポーネントの実装が継承、 **FFDasmComp**クラスおよびオーバーライド、 **GetNext**メソッド。</span><span class="sxs-lookup"><span data-stu-id="a0654-109">This component implementation inherits from the **FFDasmComp** class and overrides the **GetNext** method.</span></span> <span data-ttu-id="a0654-110">最初の呼び出しで、 **GetNext**メソッドをインターチェンジ内のすべてのメッセージを処理してに保存、 **ArrayList**から、最初のメッセージを返します、 **ArrayList**します。</span><span class="sxs-lookup"><span data-stu-id="a0654-110">On the first call to the **GetNext** method, it processes all messages in the interchange, stores them in an **ArrayList**, and returns the first message from the **ArrayList**.</span></span> <span data-ttu-id="a0654-111">後続の呼び出しで次のメッセージを返します、 **ArrayList**します。</span><span class="sxs-lookup"><span data-stu-id="a0654-111">On subsequent calls, it returns the next message from the **ArrayList**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0654-112">次のコード例の GetNext() メソッドの実装はメモリ内全体のインターチェンジを保持しているので、サイズの大きいドキュメントの処理に適切でないです。</span><span class="sxs-lookup"><span data-stu-id="a0654-112">The implementation of the GetNext() method in the code sample below would not be suitable for the processing of large documents because it retains the entire interchange in memory.</span></span>  <span data-ttu-id="a0654-113">サイズの大きいドキュメントのこの手法を使用してリソースと原因低下パフォーマンスや動作が不安定なメモリを使い果たす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0654-113">Using this technique for large documents could exhaust memory resources and cause degraded performance or unstable behavior.</span></span>  
  
```  
using System;  
using System.Collections;  
using System.Runtime.InteropServices;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.Component.Interop;  
using Microsoft.BizTalk.Component;  
  
namespace Microsoft.BizTalk.Component  
{  
   /// <summary>  
   /// Summary description for Class1.  
   /// </summary>  
   [ComponentCategory(CategoryTypes.CATID_PipelineComponent)]  
   [ComponentCategory(CategoryTypes.CATID_DisassemblingParser)]  
   [Guid("EB4714A8-FD97-43de-84E2-E011648F349B")]  
   public class TransactionalFFDasm :   
      FFDasmComp,  
      IBaseComponent,  
      IDisassemblerComponent  
   {  
      public TransactionalFFDasm()  
      {  
      }  
  
      #region IBaseComponent Members  
  
      public new string Description  
      {  
         get  
         {  
            return "Transactional Flat File Disassembler";  
         }  
      }  
  
      public new string Name  
      {  
         get  
         {  
            return "Transactional Flat File Disassembler";  
         }  
      }  
  
      public new string Version  
      {  
         get  
         {  
            return "1.0";  
         }  
      }  
  
      #endregion  
  
      #region IDisassemblerComponent Members  
  
      public new void Disassemble(IPipelineContext pContext, IBaseMessage pInMsg)  
      {  
         base.Disassemble(pContext, pInMsg);  
      }  
  
      public new IBaseMessage GetNext(IPipelineContext pContext)  
      {  
         // Check if don't need to stop collecting messages  
         if (currentMessage == 0)  
         {  
            messageInterchange = new ArrayList();  
            currentMessage = 0;  
  
            // Collect messages from the standard disassembler  
            IBaseMessage disassembledMessage = null;  
            while ((disassembledMessage = base.GetNext(pContext)) != null)  
            {  
               byte[] buffer = new byte[4096];  
               int count = 0;  
  
               // Create a new memory stream to contain the disassembled message.  
               MemoryStream messageStream = new MemoryStream();  
  
               // Get a stream pointer to the disassembled stream.  
               Stream disassembledStream = disassembledMessage.BodyPart.GetOriginalDataStream();  
  
               // Write the disassembled message to the memory stream  
               while (0 != (count == disassembledStream.Read(buffer, 0, 4096)))  
               {  
                  messageStream.Write(buffer, 0, count);  
               } // end-while  
  
               // Rewind the stream to the beginning  
               messageStream.Seek(0, SeekOrigin.Begin);  
  
               // Replace the stream on the disassembled message with the memory stream.  
               disassembledMessage.BodyPart.data = messageStream;  
  
               // Add this message to the ArrayList of messages.  
               messageInterchange.Add(disassembledMessage);  
            } // end-while  
  
            // Check if no messages were collected, just return nothing  
            if (0 == messageInterchange.Count)  
               return null;  
         } // end-if  
  
         // Check if all collected messages are returned  
         if (currentMessage == messageInterchange.Count)  
            return null;  
  
         // Return the current collected message  
         return (IBaseMessage)messageInterchange[currentMessage++];  
      } // end-method GetNext()  
  
      #endregion  
  
      private ArrayList messageInterchange = null;  
      private int currentMessage = 0;  
   }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0654-114">参照</span><span class="sxs-lookup"><span data-stu-id="a0654-114">See Also</span></span>  
 [<span data-ttu-id="a0654-115">逆アセンブラー パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="a0654-115">Developing a Disassembling Pipeline Component</span></span>](../core/developing-a-disassembling-pipeline-component.md)